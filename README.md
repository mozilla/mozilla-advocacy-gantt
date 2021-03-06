# Github issues Gantt for Mozilla Advocacy


![Gantt Diagram](screenshot.png?raw=true "GitHub Issues Gantt")


## Installation

Requires Node.js

* Clone the git repository, and install dependencies

````sh
$ git clone git://github.com/mozilla/mozilla-advocacy-gantt.git
$ cd mozilla-advocacy-gantt
$ npm install
````

## Configuration

Copy sample.env to .env - `cp sample.env .env` and edit it to set your dev environment

* Server Environment Config
    * `GITHUB_OAUTH_TOKEN`: Oauth Token with public repo access. https://github.com/settings/tokens
    * `GITHUB_REPO`: The repo to fetch issue and milestone data from
    * `GITHUB_USER`: The GitHub user/org that owns the repo
    * `PORT`: The port number that the server should listen for connections on 

* Client Side
    * modify public/config.js as required

## Custom colors per developer

In public/stylesheets/style.css
Add the lines:


````css
.fn-gantt .ganttUser1 { background-color: #DCBFEE; } // The color of the issue
.fn-gantt .ganttUser1 .fn-label { color: #4F1D6B; } // The color of the issue text
````

to the end somewhere.
Change 'User1' to anything so long as it is the same for both. You can also add as many users as you want.
Change the '#DCBFEE' to any HTML color. 
Change the '#4F1D6B' to a darker version of the first color. (Or have light text, and dark issues....)

Next, in public/config.js
Find the line:
````js
"unassigned": "ganttRed"
````
and before it, add the line:

````js
    "MySuperAwesomeGitHubUsername": "ganttUser1",
````

Take note: 
Username is case sensitive.
Use the same style as you added to the .css file.
Remember to add a comma at the end of the line. (Page will not load charts if there is a syntax error)







## Start the server

    npm start

Open http://localhost:8080

/!\ The issues are downloaded ONLY the first time you access the page.

## In GitHub

* You can set the duration of each ticket by adding a label "1D" (1 day), "2D" (2 days), ...


## TODO

* fix bug: when tickets overlap holidays

* Add a refresh button



## Credits

 * @neyric: https://github.com/neyric/gh-issues-gantt
 * Jquery Gantt widget: http://taitems.github.com/jQuery.Gantt/
