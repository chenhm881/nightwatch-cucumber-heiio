# nightwatch-cucumber-heiio
nightwatch integrate cucumber
cucumber.js 
module.exports = {
    default: {
        format: [
          'json:reports/cucumber.json'
        ]
        parallel: 4, 
    }
  }

--require setup_cucumber_runner.js  
--require features/step_definitions/*.js  
--require support/hook.js  
--format json:reports/cucumber.json  
--parallel 4   

setup_cucumber_runner.js  ->　https://github.com/nightwatchjs/nightwatch/blob/main/lib/runner/test-runners/cucumber/_setup_cucumber_runner.js

## nightwatch.config.js

test_runner: {
  type: 'cucumber',
  options: {
    feature_path: 'examples/cucumber-js/*/*.feature',
    auto_start_session: false
  }
}

## hook.js

const {Before} = require('@cucumber/cucumber');

Before(async function(testCase) {
  if (!this.client) {
    console.error('Nightwatch instance was not created.');

    return;
  }

  this.client.updateCapabilities({
    testCap: 'testing'
  });

  this.browser = await this.client.launchBrowser();
});

