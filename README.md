# Pager Beauty [![CircleCI](https://circleci.com/gh/sergiitk/pagerbeauty/tree/master.svg?style=shield)](https://circleci.com/gh/sergiitk/pagerbeauty/tree/master) [![dependencies Status](https://david-dm.org/sergiitk/pagerbeauty/status.svg)](https://david-dm.org/sergiitk/pagerbeauty) [![devDependencies Status](https://david-dm.org/sergiitk/pagerbeauty/dev-status.svg)](https://david-dm.org/sergiitk/pagerbeauty?type=dev)

Add concise PagerDuty on-calls widget to your wallboard

![PagerDuty On Call](https://user-images.githubusercontent.com/672669/46779296-1e233100-cce5-11e8-897c-b60f935e3ca8.png)

## Running
### Using Docker

```sh
docker run --rm -p 8080:8080 --env-file=.env -it sergiitk/pagerbeauty:latest
```

### Configuration

Configure PagerBeauty with `.env` file or by exporting environment variables:

```sh
# For Docker compatibility, do not placed quotation marks around the values.
# https://docs.docker.com/compose/env-file/

# PagerDuty API key
PAGERBEAUTY_PD_API_KEY=yourkey

# A list of schedule ids to load
PAGERBEAUTY_PD_SCHEDULES=SCHEDL1,SCHEDL2
# Optional: How often to refresh schedules list, in minutes. Defaults to 10.
PAGERBEAUTY_REFRESH_RATE_MINUTES=10

# Optional: Enable basic http authentication
PAGERBEAUTY_HTTP_USER=basic_username
PAGERBEAUTY_HTTP_PASSWORD=basic_password

# Optional: Local time zone, defaults to server timezone
# https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
TZ=America/New_York
```

## Add to DataDog wallboard

![Add PagerDuty to DataDog wallboard](https://user-images.githubusercontent.com/672669/46853316-ad0a7900-cdcb-11e8-80b3-ddedb7c8f2eb.gif)

1. Open the schedules list `/v1/schedules.html`
2. Find the schedule you want to embed
3. Open your DataDog dashboard, click "Edit Board".
4. Drag "IFrame" widget to the board
5. Copy PagerBeauty URL of your schedule and paste to IFrame URL on DataDog board

## Roadmap

This project is under active development.

- [x] Load and process oncalls
- [x] JSON response
- [x] HTML response
- [x] HTML responsive layout
- [x] Basic autorefresh
- [x] MVP: Embed in DataDog dashboard as an iframe
- [x] Show dates in local time
- [x] Configurable refresh period
- [x] HTTP Basic Authentication
- [ ] Full README.md and examples
- [ ] Unit testing
- [ ] Load all API pages
- [ ] Ajax refresh
- [ ] Change color to red when an incident is triggered
- [ ] Functional testing
- [ ] Automated builds
- [ ] Next on duty
- [ ] Websocket refresh

## Contributing

[Contribution guide](CONTRIBUTING.md) and step-by-step local development instructions.

The source code of [Pager Beauty](https://github.com/sergiitk/pagerbeauty) is maintained by [@sergiitk](https://github.com/sergiitk).
It's an Open Source project under MIT License. Contributions are welcomed. Follow the usual GitHub Pull Request process.

[Be nice.](CODE_OF_CONDUCT.md)

#### Questions?
Ask me on Twitter: [@sergiitk](https://twitter.com/sergiitk)


## License

Pager Beauty is released under the [MIT License](https://opensource.org/licenses/MIT).
