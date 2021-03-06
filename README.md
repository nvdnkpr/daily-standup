# daily-standup

Command-line tool for posting what you did today and the GitHub commits from
yesterday to HipChat.

If an Asana API key is specified, the next due task is used for today's work.

## Installation

    npm install --global daily-standup

## Usage

    daily-standup <message> [--config <path>]

### Example

    daily-standup "Today I'm going to implement OAuth2."

Posts the following message to HipChat:

    Today I'm going to implement OAuth2. Since yesterday I've done:
    * Add sign-in page (bloodhound/website 034cb8)
    * Add landing page (bloodhound/website b32089)
    * Fix bug with authentication (bloodhound/api eda96d)

### Options

`-h, --help` output usage information  
`-V, --version` output the version number  
`--config <path>` JSON configuration

## Configuration

daily-standup requires a `standup.json` in the directory it is run from.

### standup.json

The `standup.json` specifies the API keys to use:

    {
      // If no repos specified, all repos will be pulled (public and private)
      "repos": [
        "bloodhound/api", "bloodhound/website"
      ],
      "room": 151902, // HipChat room ID to send report to.
      "projects": [35135315, 34134314], // Optionally restrict to these Asana projects.
      "keys": {
        "asana":   "1P6flnOm.kxJMhQ2JeUyd2fOKVVHM8"
        "github":  "9dc855c5498c9318179b2e7f8c5dc486133708",
        "hipchat": "ai5K1PQErRKitNHeOgDiUcXaZJBjWjbSkdUARP"
      }
    }

## MIT Licensed
