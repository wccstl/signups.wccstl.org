#!/usr/bin/env ruby

require 'html/proofer'

desc "clean"
task :clean do
  if Dir.exists?('_site') then
    rm_rf '_site'
  end
end

desc "build the site"
task :build do
  sh "bundle exec jekyll build"
end

desc "Check the quality of the HTML output"
task :proof do
  HTML::Proofer.new("./_site", { :verbose => true, :check_html => true,
                                 :check_favicon => true, :check_external_hash => true }).run
end

desc "Default task is to clean and build"
task :default => [ :clean, :build, :proof ] do
  puts "Task complete"
end
