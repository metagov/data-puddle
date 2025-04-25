# Evocracy

The Evocracy decision-making protocol contains two steps:

1. Assign participants to groups (currently only random assignment is supported) where they work on a common solution
2. After group work, evaluate elections within groups and determine representatives for each group

Representatives are again assigned to new groups (taking their previous group document with them), so step 1 and 2 are looped until only a single group remains.

### Options

* Choose the group size
* Select an assignment method
  * Random
  * Min diversity within groups (not available yet, as of 2025-04)
  * Max diversity within groups (not available yet, as of 2025-04)
* Various voting methods, e.g. binary, ranked, rated
* Choose number of representatives per group (default: 1)
* Control self voting (default: false)

### Contact

* Open Evocracy API: https://gitlab.com/evocracy/open-evocracy-api
* Quic (uses the API): https://gitlab.com/quic-project
* Contact point for collaboration: Carlo Michaelis
  * carlo@evocracy.org
  * https://www.linkedin.com/in/carlo-michaelis/

## Examples

### Assign groups

#### Input

```
{
  "participants": [
    {
      "id": "123ab01"
    },
    {
      "id": "123ab02"
    },
    {
      "id": "123ab03"
    },
    {
      "id": "123ab04"
    },
    {
      "id": "123ab05"
    },
    {
      "id": "123ab06"
    },
    {
      "id": "123ab07"
    },
    {
      "id": "123ab08"
    },
    {
      "id": "123ab09"
    },
    {
      "id": "123ab10"
    }
  ],
  "group_size": 3
}
```

#### Output

```
[
  [
    {
      "id": "123ab07"
    },
    {
      "id": "123ab04"
    },
    {
      "id": "123ab10"
    }
  ],
  [
    {
      "id": "123ab05"
    },
    {
      "id": "123ab02"
    },
    {
      "id": "123ab09"
    }
  ],
  [
    {
      "id": "123ab01"
    },
    {
      "id": "123ab03"
    },
    null
  ],
  [
    {
      "id": "123ab08"
    },
    {
      "id": "123ab06"
    },
    null
  ]
]
```

### Determine Representatives

#### Input

```
{
  "groups": [
    [
      {
        "id": "123ab07"
      },
      {
        "id": "123ab04"
      },
      {
        "id": "123ab10"
      }
    ],
    [
      {
        "id": "123ab05"
      },
      {
        "id": "123ab02"
      },
      {
        "id": "123ab09"
      }
    ],
    [
      {
        "id": "123ab01"
      },
      {
        "id": "123ab03"
      },
      null
    ],
    [
      {
        "id": "123ab08"
      },
      {
        "id": "123ab06"
      },
      null
    ]
  ],
  "ratings": [
    [
      [ 0, 0, 1 ],
      [ 0, 0, 1 ],
      [ 1, 0, 0 ]
    ],
    [
      [ 0, 0, 1 ],
      [ 0, 0, 1 ],
      [ 1, 0, 0 ]
    ],
    [
      [ 0, 1, 0 ],
      [ 1, 0, 0 ],
      [ 0, 0, 0 ]
    ],
    [
      [ 0, 1, 0 ],
      [ 1, 0, 0 ],
      [ 0, 0, 0 ]
    ]
  ]
}
```

#### Output

```
[
  {
    "id": "123ab10"
  },
  {
    "id": "123ab09"
  },
  {
    "id": "123ab03"
  },
  {
    "id": "123ab06"
  }
]
```
