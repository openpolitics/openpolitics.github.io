require 'html-proofer'

task :rebuild do
  sh "rm -rf _site"
  sh "bundle exec jekyll build"
end

task :htmlproofer => :rebuild do
  ignored = [
    "https://votebot.openpolitics.org.uk/"
  ]
  HTMLProofer.check_directory("./_site", 
    typhoeus: {ssl_verifypeer: false, ssl_verifyhost: 0, timeout: 30},
    check_html: true, 
    url_ignore: ignored,
    assume_extension: ".html",
    check_favicon: true).run
end

task :default => :htmlproofer