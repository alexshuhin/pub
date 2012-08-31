desc 'Make html index file from haml'
task :parse do
  print 'Converting index.haml to index.html ... '
  `haml index.haml index.html`
  puts 'done'
end

desc 'Watch for changes'
task :watch do
  require 'filewatcher'
  FileWatcher.new(['index.haml']).watch do |filename|
    Rake::Task[:parse].reenable
    Rake::Task[:parse].invoke
  end
end