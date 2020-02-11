require 'rake-jekyll'

# This task builds the Jekyll site and deploys it to a remote Git repository.
# It's preconfigured to be used with GitHub and Travis CI.
# See https://github.com/jirutka/rake-jekyll for more options.
Rake::Jekyll::GitDeployTask.new(:deploy) do |t|
    t.committer = '招文桃 <zhao@wen-tao.com>'
    t.deploy_branch = -> {
        gh_user = ENV['TRAVIS_REPO_SLUG'].to_s.split('/').first
        remote_url.match(/[:\/]#{gh_user}\.github\.io\.git$/) ? 'master' : 'gh-pages'
      }
end