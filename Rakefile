require 'html-proofer'

task :test do
  sh "bundle exec jekyll build"
  ignore = [
    'https://githubeditor.herokuapp.com'
  ]
  HTMLProofer.check_directory("./_site", {href_ignore: ignore, typhoeus: { ssl_verifypeer: false }}).run
end

task :default => :test
