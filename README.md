# meteor-pr-8702

Test app for PR https://github.com/meteor/meteor/pull/8702.

## Prerequisites

- Requires a local installation of [nginx](https://www.nginx.com).

## Installation

1. `git clone https://github.com/hwillson/meteor-pr-8702.git`
2. `cd meteor-pr-8702/socket-test`
3. `[PR 8702 meteor checkout]/meteor build ../build/`
4. `cd ../build/; tar -xzvf socket-test.tar.gz`
5. `cd bundle/programs/server; meteor npm i`

## Running

1) Start a non-daemon based version of nginx using the config stored with the app:

```
cd meteor-pr-8702
nginx -c ./nginx.conf
```

2) `cd meteor-pr-8702/build/bundle`
3) `ROOT_URL=http://localhost PORT=/tmp/socktest.sock [PR 8702 meteor checkout]/meteor node main.js`
4) Access http://localhost:2048. Nginx and the test app are now communicating via the socket file located at `/tmp/socktest.sock`.
