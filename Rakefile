# Run tasks with 'rake' followed by the task name

task :serve do
  sh 'bundle exec middleman'
end

task :build do
  puts 'Building pages...'
  sh 'bundle exec middleman build'
end

# Publish to git branch
task :publish do
  puts 'Publishing build to branch...'
  sh 'git subtree push --prefix build github gh-pages'
end

# if full project is pushed to gh-pages and the repository
# needs to be overwritten with just the build folder
task :fix_gh_pages do
  sh 'git subtree split --prefix build gh-pages'
  sh "git push github $1:gh-pages --force"
end