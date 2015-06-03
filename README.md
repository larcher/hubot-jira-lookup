# Jira Issue lookup script for Hubot

## Installation

Add the package `hubot-jira-lookup` as a dependency in your Hubot `package.json` file.

	"dependencies": {
		"hubot-jira-lookup": "git://github.com/jivesoftware/hubot-jira-lookup.git"
	}

Run the following command to make sure the package is installed.

	$ npm install

To enable the script, add the `hubot-jira-lookup` entry to the `external-scripts.json` file (you may need to create this file, if it is not present or if you upgraded from Hubot < 2.4).

	["hubot-jira-lookup"]

## Configuration

There are three configuration values required for jira-lookup to work properly.

* HUBOT_JIRA_LOOKUP_USERNAME
* HUBOT_JIRA_LOOKUP_PASSWORD
* HUBOT_JIRA_LOOKUP_URL

There are also some optional configuration values.

* HUBOT_JIRA_LOOKUP_IGNORE_USERS
* HUBOT_JIRA_LOOKUP_PROJECT_KEY_REGEX

`HUBOT_JIRA_LOOKUP_IGNORE_USERS` will allow you to ignore messages from pre-defined users. Default is to ignore from users named "jira" and "github", casing is ignored.

`HUBOT_JIRA_LOOKUP_PROJECT_KEY_REGEX` allows you to specify which JIRA project keys Hubot should listen for.  Default is "[a-z]{2,5}" -- any 2 to 5 letter string.  You could expand that to catch 6 letter project keys with "[a-z]{2,6}"; or listen only for the project keys "FOO" and "BAR" (issues matching FOO-### or BAR-###) with the regex "(FOO|BAR)".

If you're using [Hubot Slack Attachments](inkel/hubot-slack-attachment), this script will use [Slack Attachments](https://api.slack.com/docs/attachments) to format its lookup result.
