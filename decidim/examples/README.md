# Open Data files for Nightly Decidim


This ZIP file contains files for studying and researching about this participation platform.


## Core

### moderations

* id: The unique identifier of the moderation
* hidden_at: Date and time when the content has been hidden
* report_count: The number of times it has been reported
* reported_url: The url of the reported resource
* reportable_type: Type of the reportable
* reportable_id: The unique id of the reportable
* reported_content: The content that has been reported
* reports: A list of reasons for which the resource has been reported


### users

* id: The unique identifier of the user
* name: The display name of user
* nickname: The username of the user
* about: The about text of the user
* avatar_url: The avatar of the user
* profile_url: The profile url
* direct_messages_enabled: Whether the user allows direct messages
* deleted: Whether the user is deleted or not
* badge: The badge of the user
* groups: The id and name of the user group


### user_groups

* id: The unique identifier of the user group
* name: The display name of user group
* nickname: The username of the user group
* avatar_url: The avatar of the user group
* profile_url: The profile url
* deleted: Whether the user is deleted or not
* badge: The badge of the user group
* members_count: The number of the users belonging to the user group
* members: The id and name of the users belonging to the group


### taxonomies

* id: The unique identifier of this taxonomy
* name: The name of this taxonomy
* parent_id: The unique identifiers of this taxonomy parent (if any)
* weight: The order in which this taxonomy is shown
* children_count: The count of the children that this taxonomy has
* taxonomizations_count: The count of the resources that use this taxonomy
* created_at: The date when this taxonomy was created
* updated_at: The date when this taxonomy was updated for the last time
* filters_count: The number of filters that is using this taxonomy
* filter_items_count: The number of items filters that are using this taxonomy
* part_of: Used to detect if this taxonomy is part of another taxonomy
* is_root: True if this taxonomy do not have any parent



## Spaces

### participatory_processes

* id: The unique identifier of this process
* title: The process title
* slug: The process slug (used for identification purposes, for the URL)
* reference: The unique reference of the space
* created_at: The date this space was created
* updated_at: The last date this space was updated
* published_at: The date this space was published
* follows_count: The number of users following this space
* hashtag: The process hashtag, used for Twitter/X
* short_description: A short description of the process
* description: A long description of the process
* promoted: Wheter the process is promoted or not
* url: The URL of the space
* subtitle: The subtitle of the process
* remote_hero_image_url: The URL of the process hero image
* announcement: The announcement (callout) information
* start_date: The start date of the process
* end_date: The end date of the process
* developer_group: The developer group of the process. This is the organization that is promoting the process.
* local_area: The local area of the process. This is the organization area where the process is taking place.
* meta_scope: The scope metadata of the process
* participatory_scope: The participatory scope of the process
* participatory_structure: The participatory structure of the process. This is how the process is decided.
* target: The target of the process. This is who is called to participate in the process.
* area: The area where the process is taking place
* participatory_process_group: The group of the process, if there is any
* scope: The scope of the process
* scopes_enabled: Whether the scopes are enabled or not
* participatory_process_type: The type of the process


### assemblies

* id: The unique identifier of this assembly
* title: The assembly title
* slug: The assembly slug (used for identification purposes, for the URL)
* reference: The unique reference of the space
* created_at: The date this space was created
* updated_at: The last date this space was updated
* published_at: The date this space was published
* follows_count: The number of users following this space
* hashtag: The assembly hashtag, used for Twitter/X
* short_description: A short description of the assembly
* description: A long description of the assembly
* promoted: Wheter the assembly is promoted or not
* url: The URL of the space
* subtitle: The subtitle of the assembly
* remote_hero_image_url: The URL of the assembly hero image
* remote_banner_image_url: The URL of the assembly banner image
* announcement: The announcement (callout) information
* developer_group: The developer group of the assembly
* local_area: The local area of the assembly
* meta_scope: The scope metadata of the assembly
* participatory_scope: The participatory scope of the assembly
* purpose_of_action: The purpose of action of the assembly
* composition: The composition of the assembly
* duration: The duration of the assembly
* participatory_structure: The participatory structure of the assembly
* target: The target of the assembly
* decidim_scope_id: The scope of the assembly
* area: The area of the assembly
* scope: The scope of the assembly
* scopes_enabled: Weather the scopes are enabled or not
* included_at: The date when the assembly was included
* closing_date: The closing date of the assembly
* created_by: Who has created this assembly
* creation_date: The date of creation of this assembly
* closing_date_reason: Why the assembly was closed
* internal_organisation: The internal organisation of this assembly
* is_transparent: Where the assembly is transparent or not
* special_features: Which special features this assembly has
* twitter_handler: Social media handler for Twitter
* instagram_handler: Social media handler for Instagram
* facebook_handler: Social media handler for Facebook
* youtube_handler: Social media handler for YouTube
* github_handler: Social media handler for GitHub
* created_by_other: Other creator of the assembly
* assembly_type: The type of the assembly


### conferences

* id: The unique identifier of this conference
* title: The conference title
* slug: The conference slug (used for identification purposes, for the URL)
* reference: The unique reference of the space
* created_at: The date this space was created
* updated_at: The last date this space was updated
* published_at: The date this space was published
* follows_count: The number of users following this space
* hashtag: The conference hashtag, used for Twitter/X
* short_description: A short description of the conference
* description: A long description of the conference
* promoted: Wheter the conference is promoted or not
* url: The URL of the space
* slogan: The slogan for this conference
* remote_hero_image_url: The URL of the conference hero image
* remote_banner_image_url: The URL of the conference banner image
* location: The conference location. Where this conference will take place.
* objectives: The objectives for this conference. What is the goal.
* start_date: The date when this conference starts.
* end_date: The date when this conference ends.
* scopes_enabled: Weather the scopes are enabled or not
* decidim_scope_id: The scope of the conference
* scope: The scope of the conference


### initiatives

* reference: The unique reference of the space
* title: The title of the initiative
* url: The URL of the space
* description: The description of the initiative
* state: The state that this initiative has in this moment
* created_at: The date this space was created
* updated_at: The last date this space was updated
* published_at: The date this space was published
* signature_start_date: The date when the signature collection period started
* signature_end_date: The date when the signature collection period ends
* signature_type: The type of signature collection (online or in-person)
* signatures: The number of signatures that this initiative has
* answer: The answer that this initiative has received (if any)
* answered_at: The date of the answer (if any)
* answer_url: The URL of the answer (if any)
* hashtag: The initiative hashtag, used for Twitter/X
* first_progress_notification_at: The date when the first progress notification was sent
* second_progress_notification_at: The date when the second progress notification was sent
* online_votes: The number of signatures that this initiative received online (directly through the platform)
* offline_votes: The number of signatures that this inititative received outside of this platform
* comments_count: The number of comments that this initiative has
* follows_count: The number of users following this space
* scope: The scope of the initiative
* type: The type of the initiative
* authors: The authors of this initiative
* area: The area of this initiative



## Components

### results

* id: The unique identifier of the result
* taxonomies: The taxonomies of the result
* parent: The parent result (if any) of the result
* title: The title of the result
* description: The description of the result
* start_date: The date when the result starts execution
* end_date: The date when the result ends execution and it is finished
* status: The current status of this result
* progress: The percentage of the execution of the result
* created_at: The date when the result was created
* updated_at: The last date this result was updated
* url: The URL where this result can be found
* component: The component that the result belongs to
* proposal_urls: The URLs of the proposals that are included in this result
* reference: The unique reference of the result
* children_count: The number of child results
* comments_count: The number of comments that this result has
* address: The address of the result (if any)
* latitude: The latitude of the result in case it has a physical location
* longitude: The longitude of the result in case it has a physical location


### result_comments

* id: The id for this comment
* created_at: The date when this comment was created
* body: The comment itself
* locale: The locale (language) that the participant had when leaving this comment
* author: The name of the participant that made this comment
* alignment: If this comment was a favour, against or neutral
* depth: The place where this comment is in the three of comments (if it is an answer or an answer of an answer)
* user_group: The name of the user group that made this comment (if any)
* commentable_id: The unique id of the commentable
* commentable_type: The type of the commentable (if it was a result, a proposal, etc.)
* root_commentable_url: The URL of the resource that ties to this comment


### posts

* id: The unique identifier of this post
* author: The information of the author
* title: The title of the post
* body: The body of the post
* created_at: The date this post was created
* updated_at: The last date this post was updated
* published_at: The date this post was published
* endorsements_count: The number of endorsements this post has
* comments_count: The number of comments this post has
* follows_count: The number of follows this post has
* participatory_space: To which space (e.g. Participatory Process, or Assembly) this post belongs to
* component: The component that the post belongs to
* url: The URL for this post


### post_comments

* id: The id for this comment
* created_at: The date when this comment was created
* body: The comment itself
* locale: The locale (language) that the participant had when leaving this comment
* author: The name of the participant that made this comment
* alignment: If this comment was a favour, against or neutral
* depth: The place where this comment is in the three of comments (if it is an answer or an answer of an answer)
* user_group: The name of the user group that made this comment (if any)
* commentable_id: The unique id of the commentable
* commentable_type: The type of the commentable (if it was a result, a proposal, etc.)
* root_commentable_url: The URL of the resource that ties to this comment


### projects

* id: The unique identifier of the project
* taxonomies: The taxonomies of the project
* participatory_space: To which space (e.g. Participatory Process, or Assembly) this project belongs to
* component: The component that the project belongs to
* title: The title of the project
* description: The description of the project
* budget: Data regarding the budget (e.g. "2021 Budget") of the project
* budget_amount: The total amount of the budget for this project
* confirmed_votes: The number of confirmed votes this project has received
* comments: The number of comments this project has received
* created_at: The date and time when the project was created
* url: The URL of the project
* address: The address of the project (if any)
* updated_at: The last date the project was updated
* selected_at: The time at which the project was selected
* reference: The unique reference of the project
* follows_count: The number of follows the project has
* latitude: The latitude of the project in case it has a physical location
* longitude: The longitude of the project in case it has a physical location
* related_proposals: The related proposals to this project
* related_proposal_titles: The titles of the related proposals
* related_proposal_urls: The URLs of the related proposals


### debates

* id: The unique identifier of the debate
* author: The data for the author of this debate
* title: The debate title
* description: The debate description
* instructions: Which are the instructions to comment in this debate
* start_time: When this debate starts, if it is an open debate and has a limited time
* end_time: When this debate ends, if it is an open debate and has a limited time
* information_updates: The updates that the author has made to the debate
* taxonomies: The taxonomies of the project
* participatory_space: To which space (e.g. Participatory Process, or Assembly) this debate belongs to
* component: The component that the debate belongs to
* reference: The unique identifier of the resource in this platform
* comments: The number of comments this debate has
* follows_count: The number of followers this debate has
* url: The URL where this debate can be found
* last_comment_at: The date when this debate was commented by the last time
* last_comment_by: The data of last comment made within the debate
* comments_enabled: Wether this debate has comments enabled or not
* conclusions: The conclusions of the debate if it was closed
* closed_at: The date when this debate was closed
* created_at: The date and time when the debate was created
* updated_at: The date of when the debate was last updated
* endorsements_count: The number of endorsements the debate has


### debate_comments

* id: The id for this comment
* created_at: The date when this comment was created
* body: The comment itself
* locale: The locale (language) that the participant had when leaving this comment
* author: The name of the participant that made this comment
* alignment: If this comment was a favour, against or neutral
* depth: The place where this comment is in the three of comments (if it is an answer or an answer of an answer)
* user_group: The name of the user group that made this comment (if any)
* commentable_id: The unique id of the commentable
* commentable_type: The type of the commentable (if it was a result, a proposal, etc.)
* root_commentable_url: The URL of the resource that ties to this comment


### meetings

* id: The unique identifier of the meeting
* author: The data for the author of this meeting
* participatory_space: To which space (e.g. Participatory Process, or Assembly) this meeting belongs to
* taxonomies: The taxonomies that this meeting belongs to
* component: The component that the meeting belongs to
* title: The title of the meeting
* description: The description of the meeting
* start_time: The date and time that this meeting starts
* end_time: The date and time that this meeting ends
* attendees: The number of people attending this meeting
* contributions: The number of contributions in this meeting made by the atteendes
* organizations: The organizations attending this meeting
* address: The address of the meeting in case it is in person and has a physical location
* location: The location of the meeting
* reference: The unique identifier of the resource in this platform
* attachments: The number of attachments in this meeting
* url: The URL of the meeting
* related_proposals: The proposals related to this meeting
* related_results: The results related to this meeting
* published: When the meeting has been published
* withdrawn: Whether this meeting has been withdrawn
* withdrawn_at: When this meeting was withdrawn
* location_hints: A hint of the location in which the meeting is taking place
* created_at: The date at which the meeting was created
* updated_at: The time at which the meeting was last updated
* latitude: The latitude of the meeting
* longitude: The longitude of the meeting
* follows_count: The number of follows the meeting has
* private_meeting: To indicate whether the meeting is private or not
* transparent: The visabilty of the meetng for non-members
* registration_form_enabled: Whether the registration form was enabled or not
* comments: The comments data of the meeting
* online_meeting_url: The URL of the online meeting
* closing_visible: The visibilty of the meeting
* closing_report: Report of the closed meeting
* attending_organizations: The organizations attending the meeting
* registration_url: URL of the meeting registration
* decidim_user_group_id: User group ID of people involved in the meeting
* decidim_author_type: Author type of the meeting's author
* video_url: Video recording of the meeting
* audio_url: Audio recording of the meeting
* closed_at: The date at which the meeting closed
* registration_terms: The terms agreed prior to meeting participation
* available_slots: The number of slots available in a meeting
* registrations_enabled: Whether registrations were permitted
* customize_registration_email: The ability to allow a custom email at registration
* type_of_meeting: The meeting type
* iframe_access_level: The iframe access level of the meeting
* iframe_embed_type: The type of iframe embeded in the meeting
* reserved_slots: The number of reserved slots the meeting has
* registration_type: The type of registration of the meeting


### meeting_comments

* id: The id for this comment
* created_at: The date when this comment was created
* body: The comment itself
* locale: The locale (language) that the participant had when leaving this comment
* author: The name of the participant that made this comment
* alignment: If this comment was a favour, against or neutral
* depth: The place where this comment is in the three of comments (if it is an answer or an answer of an answer)
* user_group: The name of the user group that made this comment (if any)
* commentable_id: The unique id of the commentable
* commentable_type: The type of the commentable (if it was a result, a proposal, etc.)
* root_commentable_url: The URL of the resource that ties to this comment


### pages

* id: The unique identifier of this page
* title: The page title
* body: The body of the page
* created_at: The date this page was created
* updated_at: The last date this page was updated
* participatory_space: To which space (e.g. Participatory Process, or Assembly) this page belongs to
* component: The component that the page belongs to
* url: The URL for this page


### proposals

* id: The unique identifier for the proposal
* author: The data for the author of this proposal
* taxonomies: The taxonomies that this proposal belongs to
* participatory_space: To which space (e.g. Participatory Process, or Assembly) this proposal belongs to
* component: The component that the proposal belongs to
* title: The proposal title
* body: The proposal body
* address: The address of the proposal in case the proposal has a physical location
* latitude: The latitude of the proposal in case it has a physical location
* longitude: The longitude of the proposal in case it has a physical location
* state: The status of this proposal (e.g. "Accepted")
* state_published_at: A time stamp of the state of the proposal when published
* reference: The unique identifier of the resource in this platform
* answer: The answer to the proposal in the case it has been answered
* answered_at: The date when this proposal was answered
* votes: The number of votes this proposal has
* endorsements: The number of endorsements ("likes") this proposal has
* comments: The number of comments this proposal has
* attachments: The number of attachments this proposal has
* follows_count: The number of followers this proposal has
* published_at: The date when this proposal was published
* url: The URL where this proposal can be found
* meeting_urls: The URLs of the meetings where this proposal was presented or discussed in
* related_proposals: The proposals related to this proposal
* is_amend: Wheter this proposal is ammedning another proposal
* original_proposal: The reference of the original proposal if this is an amendment
* withdrawn: Wheter this proposal has been withdrawn
* withdrawn_at: When this proposal was withdrawn
* created_at: The date the proposal was created
* updated_at: The date the proposal was last updated
* created_in_meeting: Whether the proposal was created in a meeting
* coauthorships_count: The number of co-authorships the proposal represents
* cost: The total cost of the proposal in question
* cost_report: A report of costs for the proposal
* execution_period: The period at which the proposal ran from beginning to end


### proposal_comments

* id: The id for this comment
* created_at: The date when this comment was created
* body: The comment itself
* locale: The locale (language) that the participant had when leaving this comment
* author: The name of the participant that made this comment
* alignment: If this comment was a favour, against or neutral
* depth: The place where this comment is in the three of comments (if it is an answer or an answer of an answer)
* user_group: The name of the user group that made this comment (if any)
* commentable_id: The unique id of the commentable
* commentable_type: The type of the commentable (if it was a result, a proposal, etc.)
* root_commentable_url: The URL of the resource that ties to this comment



