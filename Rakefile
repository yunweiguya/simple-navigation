require 'rake'
require 'spec/rake/spectask'
require 'rake/rdoctask'

desc 'Default: run specs.'
task :default => :spec

desc 'Run the specs'
Spec::Rake::SpecTask.new(:spec) do |t|
  t.spec_opts = ['--colour --format progress --loadby mtime --reverse']
  t.spec_files = FileList['spec/**/*_spec.rb']
end

namespace :spec do
  desc "Run all specs with RCov"
  Spec::Rake::SpecTask.new(:rcov) do |t|
    t.spec_opts = ['--colour --format progress --loadby mtime --reverse']
    t.spec_files = FileList['spec/**/*_spec.rb']
    t.rcov = true
    t.rcov_opts = ['--exclude', 'spec,/Users/']
  end
end

desc 'Generate documentation for the simple_navigation plugin.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'SimpleNavigation'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "simple-navigation"
    gemspec.summary = "Simple Navigation is a ruby library for creating a navigation (optionally with sub navigation) for your rails app."
    gemspec.email = "andreas.schacke@gmail.com"
    gemspec.homepage = "http://github.com/andi/simple-navigation"
    gemspec.description = "Simple Navigation is a ruby library for creating a navigation (optionally with sub navigation) for your rails app."
    gemspec.authors = ["Andi Schacke"]
    gemspec.rdoc_options = ["--inline-source", "--charset=UTF-8"]
    gemspec.files += ["CHANGELOG"]
    gemspec.rubyforge_project = 'andi'
  end
  Jeweler::RubyforgeTasks.new do |rubyforge|
    rubyforge.doc_task = "rdoc"
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end
