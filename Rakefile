# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
    # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options

    gem.name = "vimeo"
    gem.summary = %Q{A full featured Ruby implementation of the Vimeo API.}
    gem.description = %Q{A full featured Ruby implementation of the Vimeo API.}
    gem.email = "jwozniak@netkodo.com"
    gem.homepage = "http://github.com/netkodo/vimeo"
    gem.authors = ["Jarek Wozniak"]
    gem.rubyforge_project = "vimeo"
    gem.add_development_dependency "shoulda", ">= 2.11.3"
    gem.add_development_dependency "fakeweb", ">= 1.2.6"
    gem.add_development_dependency "ruby-prof", ">= 0.9.2"

    gem.has_rdoc = true

    gem.rdoc_options = ['--main', 'README.rdoc', '--inline-source', '--charset=UTF-8']
    gem.extra_rdoc_files = ['README.rdoc', 'LICENSE', 'CHANGELOG.rdoc']
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*_test.rb'
  test.verbose = true
end

task :default => :test


require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "vimeo #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
