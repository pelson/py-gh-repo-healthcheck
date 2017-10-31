![](https://repohealth.info/static/img/heart.png)

# Github repository health report

This is the source for the [Github repository health report service](https://repohealth.info/) found at https://repohealth.info/.

## About

The GitHub repository health report service aims to make it simple to gather metrics about the health of repositories on GitHub.
We study a repository's commits and combine this with data available through the GitHub API to give easy to read metrics.
No single metric is a good indicator of a repository's health, and we don't try to combine the information in any way to come up with a single health "score" –
instead, we present the data in a way that will allow you to draw your own conclusions.

## Scope

This service is intended to remain simple and accessible.
Whilst it would be interesting to add more layers of sophistication (e.g. predictive metrics), the diminishing returns will quickly outweigh the cognitive
burden on maintainers of this repository - for this reason, we encourage collaboration that *simplifies* 3rd party data analysis using the APIs
that are provided by this service.

## License

This work has been funded by the [Met Office](https://www.metoffice.gov.uk/), the UK's national weather service.
The source of this repository is licensed under a BSD 3-clause license.

## Development

We have intentionally kept the development setup of this repository very simple.
The service is a single tornado web-app that can be deployed to any machine with the pre-requisite dependencies.
The full code for building the operational Heroku image can be found in [buildpack-run.sh](https://github.com/pelson/repohealth.info/blob/master/buildpack-run.sh).


When developing locally, a personal GitHub application token that points back to ```localhost:8888``` will be needed.
Next, define the ``CLIENT_ID``, ``CLIENT_SECRET`` and ``COOKIE_SECRET`` environment variables (the latter can be set to any value).
Finally, simply run ``python webapp.py`` and authenticate through to view reports locally as you would on the public service.


The service itself is running on Heroku, and whilst we could be making use of more advanced caching technologies (like a database!) we
simply rely on our deployment target's ephemeral storage to act as a data cache.


Google analytics is enabled on the service - please let @pelson know if you have contributed to this repository and want access.


## Other work

There are a number of other tools and services that provide health metrics (and scores) of Git and/or GitHub repositories:

 * https://github.com/dogweather/repo-health-check / http://repocheck.com/
 * https://github.com/gorillamania/repo-health
 * https://github.com/chillu/github-dashing
 * https://github.com/timqian/star-history

 * https://github.com/sarahsharp/foss-heartbeat
