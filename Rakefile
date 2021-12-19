require "rake/testtask"
require "find"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc "List public files"
task :list do
  Find.find(Dir.pwd) do |path|
    if File.basename(path).start_with?(".")
      Find.prune
    else
      puts File.basename(path) unless File.directory?(path)
    end
  end
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end