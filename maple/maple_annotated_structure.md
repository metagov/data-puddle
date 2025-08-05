## MAPLE Flatfile (IN Progress)

Much of the supplementary data in MAPLE (including bills, committees, legislators, and hearings) is scraped from the Massachusetts Legislature's API (available at: https://malegislature.gov/api/swagger/index.html?url=/api/swagger/v1/swagger.json#/Hearings). To start, I'm going to focus on the data that MAPLE adds itself - after chatting, we can decide whether it's worth pulling the mirrored MA Legislature data into this given the caveats.

# `events` Collection: Stores information on scheduled events in the Massachusetts Legislature (e.g. public hearings, legislative sessions, and special events) scraped from the MA Legislature API

- `id` (string): ID uniquely identifying the event
- `fetchedAt` (timestamp): The time when the event was last scraped from the Legislature's website
- `startsAt` (timestamp): The time when the event is scheduled to begin
- `type` (enum): The type of the event (e.g. "hearing" for public hearings, "session" for legislative sessions, or "specialEvent" for other special events)
- `videoFetchedAt` (timestamp): The time when the event's video was scraped (this is done separately after hearing events are completed for automatic transcription)
- `videoTranscriptionId` (string): An id that maps to an object in the Transcription collection containing the automated transcription of the event's video recording (if applicable)
- `videoURL` (string): The publically accessible URL of the hearing's video recording (if applicable)
- `content` (json): A JSON Object of the event data that is scraped directly from the legislature. This is a data blob that reflects whatever the legislature's API returns for a given event, but common subfields are:
  - `Description` (string): A short description of the event
  - `EventId` (string): A numeric id representing the event's id in the MA Legislature API
  - `Name` (string): Name of the event. In the case of hearings, the name is the name of the hosting Committee or Commission
  - `Status` (string): The current status of the event (e.g. "Completed")
  - `HearingHost` (hearings only - the Committee or Commission hosting the hearing)
    - `CommitteeCode` (string): Code of the Committee
    - `GeneralCourtNumber` (int): General Court for this Committee

# `bills` Collection: Stores information on bills on the legislative agenda for the Massachusetts Legislature.

- `id` (string): The id of the bill (e.g. "H1000" for a house bill or "S395" for a senate bill) - for reference, this is identical to the `BillNumber` in the MA Legislature API.
- `court` (int): The general court this bill was filed under
- `cosponsorCount` (int): The number of cosponsors the bill has (including the primary sponsor)
- `currentCommittee` (json): The committee currently processing the bill. Fields include:
  - `id` (string): The id of the committee in the MA Legislature API
  - `name` (string): The name of the committee (e.g. "Joint Committee on Environment and Natural Resources")
- `fetchedAt` (timestamp): The time the bill was last scraped at
- `endorseCount` (int): The number of MAPLE users who have submitted testimony endorsing the bill
- `neutralCount` (int): The number of MAPLE users who have submitted testimony with a neutral stance on the bill
- `opposeCount` (int): The number of MAPLE users who have submitted testimony with a negative stance on the bill
- `testimonyCount` (int): The total number of testimonies MAPLE users have submitted for the bill
- `latestTestimonyAt` (timestamp): The time of the most recently submitted user testimony for this bill
- `nextHearingAt` (timestamp): The time of the next hearing event with this bill on the agenda
- `summary` (string): An succinct AI-generated summary of the full bill text.
- `topics` (array): A small (generally 2-5) list of AI-generated topics based on the bill text, used for classification and search. Fields include:
  - `category` (enum): One of a fixed number of broad topic categories that describe the bill (e.g. "Healthcare" or "Environmental Protection")
  - `topic` (string): A subtopic that more specifically categorizes the bill (e.g. "Pollution control and abatement" or "Water quality" are possible `topic`s for the "Environmental Protection" category)
- `history` (array): A chronologically ordered list of bill history actions. Fields include:
  - `Action` (string): A short summary of the history event (e.g. "Referred to Committee")
  - `Branch` (enum): The branch the event occurred in (e.g. House/Senate/Joint)
  - `Date` (string): Datetime string of the time the event occurred (e.g. "2025-02-27T10:38:52.383")
- `content` (json): Bill content scraped directly from the MA Legislature's API. Noteworthy fields include:
  - `Cosponsors` (array): List of the bill's cosponsors
    - `Id` (string): Id of the legislator in the MA Legislature API (e.g. "CMM1")
    - `Name` (string): Name of the legislator
  - `DocumentText` (string): The full text of the bill
  - `PrimarySponsor` (json): The primary sponsor of the bill (with identical `Id`/`Name` fields as the above Cosponsors)
  - `Title` (string): A short name for the bill (e.g. "An Act establishing a coastal waters wastewater financing commission")

# `cities` Collection: A list of cities with home rule petitions.

- `id` (string): The city name (e.g. "Natick")
- `bills` (array[string]): A list of bill ids (e.g. "H1234") for all bills that are home rule petitions for this city.
- `court` (int): The general court these bills were filed under
- `fetchedAt` (timestamp): The time that these city bills were last scraped from the MA legislature's API

# `profiles` Collection: Stores information on public user profiles

- `id` (string): A unique string ID representing the user's profile
- `about` (string): A short blurb the user provides to summarize themselves
- `displayName` (string): The displayed name for the profile (e.g. "John Smith" or "The Society of Lorem Ipsum")
- `public` (boolean): Boolean value - when false, other users are not allowed to subscribe to notifications for this profile and links to this profile from public testimony pages will be disabled.
- `role` (enum): The profiles's role (most commonly, `user` for private citizens and `organization` for organizations).
- `representative` (json): Object representing the profile's self-selected state representative.
- `senator` (json): Object representing the profile's self-selected state senator.
- `social` (json): Object with keys for displaying and linking to the profile's social media accounts. Examples include:
  - `fb` (string): The profile's Facebook account
  - `twitter` (string): The profile's Twitter/X account
  - `linkedIn` (string): The profile's LinkedIn account
  - `instagram` (string): The profile's Instagram account
  - `blueSky` (string): The profile's BlueSky account
  - `mastodon` (string): The profile's Mastodon account

# `transcriptions` Collection: Stores information on transcriptions of Legislative Hearing videos.

- `id` (string): The UUID assigned to this transcription.
- `createdAt` (timestamp): The time this transcription was generated.
- `text` (string): The full transcribed text of the hearing video

# `publishedTestimony` Collection: Stores information on the published testimony submitted on bills by MAPLE users

- `id` (string): A unique ID identifying this testimony
- `authorDisplayName` (string): The displayName of the profile that published the testimony (or "private" if the publishing user has their `public` flag set to `false`)
- `authorRole` (enum): The role of the profile that published the testimony (most relevantly, one of `user` for private citizens or `organization` for organizations)
- `authorUid` (string): The ID of the profile that published the testimony
- `billId` (string): The ID of the bill that the bill for which this testimony was submitted
- `billTitle` (string): The title of the bill for which the testimony was submitted (e.g. "An Act updating the citizens advisory panel and strengthening citizen participation on the panel for the decommissioning of the Pilgrim Nuclear Power Plant")
- `content` (string): The full text of the published testimony submitted by the user
- `court` (int): The general court of the bill for which this testimony was submitted
- `position` (enum): The overall position of this testimony on the bill for which it was written (one of "Endorse"/"Neutral"/"Oppose")
- `public` (boolean): A boolean flag - when false, links to the profile of this testimony's author are disabled in the UI and their name is displayed as "private".
- `publishedAt` (timestamp): The time this testimony was published to MAPLE
- `version` (int): The version number of this testimony. Default is 1.

