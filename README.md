# nightwatch-cucumber-heiio
nightwatch integrate cucumber
cucumber.js 
module.exports = {
    default: `--format json:reports/cucumber.json, --parallel 4`
  }
--require setup_cucumber_runner.js
--require features/step_definitions/*.js
--require support/hook.js
--format json:reports/cucumber.json
--parallel 4 

setup_cucumber_runner.js  ->　https://github.com/nightwatchjs/nightwatch/blob/main/lib/runner/test-runners/cucumber/_setup_cucumber_runner.js





