require 'html-proofer'

task :rebuild do
  sh "rm -rf _site"
  sh "bundle exec jekyll build"
end

task :htmlproofer => :rebuild do
  HTMLProofer.check_directory("./_site", 
    check_html: true, 
    assume_extension: ".html",
    check_favicon: true).run
end

task :default => :htmlproofer