{spawn} = require 'child_process'

task 'pretest', "Build CoffeeScript source files", ->
  coffee = spawn 'coffee', ['-c', '-o', 'lib', 'src']
  coffee.stdout.on 'data', (data) -> process.stderr.write data.toString()
  
task 'test', "Run test suite", ->
  process.chdir __dirname
  {reporters} = require 'nodeunit'
  reporters.default.run ['test']
