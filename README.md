# worcestersource.club

The group's homepage, based on the Urban Jekyll Template by [CloudCannon](http://cloudcannon.com/).

This is a fairly standard Jekyll project, with the exception that some content is generated dynamically from the [meetup.com API](https://www.meetup.com/meetup_api/) via the [jekyll-get plugin](https://github.com/18F/jekyll-get).

There is provision to use the site as a blog, but at present this isn't used.

There are also some remnants of the CloudCannon customisation which isn't utilised, such as editable content areas, and data elements like `_staff_members` and `_clients`. These have not been removed, as they could be used for blog authors and sponsors, respectively.

## Develop

This project uses the [jekyll-serve Docker image](https://github.com/BretFisher/jekyll-serve) and live-reload for development purposes, allowing for quick and easy set-up of a development environment.

Simply run docker compose, then visit <http://localhost:4000/> in the browser:

~~~bash
$ docker-compose up
~~~

If you make changes to the `_config.yml` file, you'll need to restart docker compose.

~~~bash
$ docker-compose restart
~~~

## Deployment

The site is hosted by [Netlify](https://app.netlify.com/), and configured to automatically deploy upon every commit on the `master` branch which is pushed to GitHub.

Additionally, because of the dynamic content pulled in from meetup.com, we're using [cron-job.org](https://cron-job.org/) to trigger a built of the site once a day.
