---
permalink: /configuration-file/
title: 'Configuration File'
toc_label: 'Configuration File'
---

This section documents utilization of the configuration file in place of CLI options.

## Parameters

### testPath
  * Path to tests
  * Example: `testPath: ./my-test-folder`

### components
  * Path to components
  * Example: `components: /my-components-folder`

### reporter
  * Specify a reporter to use. Either `basic` or `teamcity` 
  * Default is `basic`
  * Example: `reporter: teamcity`
    
### saucelabs
  * Flag for running tests in saucelabs. A sauce tunnel will be started
  * Must have `SAUCE_USERNAME` AND `SAUCE_ACCESS_KEY` specified
  * Example: `saucelabs: true`

### parallelism
  *  Amount of tests to run in parallel
  *  Default is `20`
  *  Example; `parallelism: 5`

### reportPath
  * The parth wherein to write the test report
  * Example: `reportPath: ./my-reports`

### before
  * The path to a before script run before the test suite
  * Must be a valid JavaScript file that exports a single function
  * Example: `before: my-before-script.js`

### outputPath
  * The path wherein to write the generated test cases
  * Default is the current working directory
  * Example `outputPath ./tests`

### technique
  * The test generation technique
  * The only and required option at this point is actionFocused
  * Example `technique actionFocused`

### actionToCover
  * The single action to generate a test to cover
  * Default is the current working directory
  * Example `actionToCover myComponent.MY_ACTION`

## Example File
    'use strict'

    module.exports = {
        testPath: './test/acceptance/tests',
        components: './test/acceptance/components',
        reportPath: './test/acceptance/tests',
        saucelabs: true
        outputPath: './test/acceptance/tests',
        technique: 'actionFocused',
    }