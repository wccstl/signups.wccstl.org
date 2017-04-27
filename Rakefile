#!/usr/bin/env ruby

require 'html-proofer'

desc "clean"
task :clean do
  if Dir.exists?('_site') then
    rm_rf '_site'
  end
end

desc "build the site"
task :build do
  sh "bundle exec jekyll build --profile"
end

desc "Check the quality of the HTML output"
task :proof do
  options = { :verbose => true, :check_html => true,
              :check_favicon => false, :check_external_hash => true,
              :assume_extension => true, :check_opengraph => true,
              :check_img_http => true, :enforce_https => true,
              :external_only => true }
  HTMLProofer.check_directory("./_site", options).run
end

desc "Default task is to clean and build"
task :default => [ :clean, :build, :proof ] do
  puts "Task complete"
end
