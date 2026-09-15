Browser Perf Logger
===

Setup
---

If you want to use any of the patched browsers that playwright maintains
(needed to run these tests with Firefox, Safari, or other Gecko or Webkit
based browsers), you'll need to run `npm run install-browsers` first.

Usage and Running
---

Run with `npm run go`.

Below is the output of `npm run go -- --help`.

    > browser-perf-logger@0.3.1 go
    > node ./dist/cli.js --help

    usage: cli.js [-h] [-a [ARGS ...]] [-d USER_DATA_DIR] [-f FIREFOX_USER_PREFS]
                [--do-not-drop] [-l {none,error,info,verbose,debug}]
                [-m [{memory-cpu,network,power,timing} ...]] [-o OUTPUT] [-r]
                [-s SECONDS] [-t TIMEOUT] [-v] [-w WEBKIT_BUILD]
                [-x BINARY_PATH] [--height HEIGHT] [--width WIDTH]
                url [browser]

    Run performance tests for a playwright version of a browser.

    positional arguments:
    url                   The URL to run measurements against. Should be a full
                            URL (i.e., at least a scheme and a domain)
    browser               Which browser family to use for this test, one of:
                            brave, chromium, gecko, webkit (default: chromium)

    optional arguments:
    -h, --help            show this help message and exit
    -a [ARGS ...], --args [ARGS ...]
                            Additional Chromium arguments that are passed along to
                            the shell when launching the browser. So, to pass the
                            argument '--disable-features=x' to the browser, pass
                            '--args disable-features=x'. (default: undefined)
    -d USER_DATA_DIR, --user-data-dir USER_DATA_DIR
                            Path to the user data directory to load and save
                            persistent state to. For Chromium browsers, this will
                            be a directory containing multiple profiles. For other
                            browsers, this directory will be the state for a
                            single profile. If not provided, will create a new
                            temporary user-data directory. *Note:* Gecko/Firefox
                            measurements should use this flag for specifying the
                            path for storing persistent user data (and not
                            --profile). (default: undefined)
    -f FIREFOX_USER_PREFS, --firefox-user-prefs FIREFOX_USER_PREFS
                            Optional JSON of Firefox about:config overrides and
                            settings. If provided, these will be applied after
                            Playwright's preference overrides. This argument can
                            only be used when the browser argument is 'gecko'.
                            (default: undefined)
    --do-not-drop         If passed, disable the default behavior of dropping
                            permissions if it looks like we're being run with
                            sudo. (default: false)
    -l {none,error,info,verbose,debug}, --logging {none,error,info,verbose,debug}
                            What level of information to include when printing
                            information during the measurement. (default: info)
    -m [{memory-cpu,network,power,timing} ...], --measurements [{memory-cpu,network,power,timing} ...]
                            Which measurements of performance to collect. By
                            default, performs all measurements. (default:
                            memory-cpu,network,power,timing)
    -o OUTPUT, --output OUTPUT
                            Path to write results to. By default results are
                            written to STDOUT, but this can instead write the
                            measurement results to a file. If --output is called
                            with the path to a directory, results will be written
                            to a file in that directory with a name derived from
                            the --url argument. If --output is called with a path
                            that matches an existing file, or a path where no file
                            exists, the results will be written to that path.
                            (default: undefined)
    -r, --preserve-pages  Preserve and reopen any pages and tabs that are set as
                            open in the specified --user-data-dir (if any). By
                            default the tool will prevent any pages from being
                            automatically opened, but if this argument is set,
                            then any existing pages will be reopened before taking
                            any measurements. (default: false)
    -s SECONDS, --seconds SECONDS
                            Number of seconds to wait while measuring page
                            performance. (default: 10)
    -t TIMEOUT, --timeout TIMEOUT
                            Number of seconds to wait for the browser to complete
                            tasks separate from loading the given page (e.g., open
                            the browser, navigate to the given URL, etc.)
                            (default: 5)
    -v, --version         show program's version number and exit
    -w WEBKIT_BUILD, --webkit-build WEBKIT_BUILD
                            Use a custom build of Webkit. This argument should be
                            the path to the root of git checkout. This argument
                            can only be used i. when the --browser (-b) argument
                            is 'webkit' and cannot be used with the --binary-path
                            (-x) argument. (Only supported on MacOS builds
                            currently.) (default: undefined)
    -x BINARY_PATH, --binary-path BINARY_PATH
                            Path to the browser binary to run the measurements
                            with. (default: undefined)
    --height HEIGHT       The height of the browser viewport to use when loading
                            pages. (default: 720)
    --width WIDTH         The width of the browser viewport to use when loading
                            pages. (default: 1280)
