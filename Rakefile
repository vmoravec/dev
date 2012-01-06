namespace :install do
  desc "Vim configuration"
  task :vim do
    vim_configuration 'vim'
  end

  desc "Install everything"
  task :all do
    everything
  end
end

desc "List of the tasks"
task :default do
  Rake::TaskManager.record_task_metadata = true
  rake = Rake::Application.new
  Rake.application = rake
  rake.init
  rake.options.show_tasks = :tasks
  rake.options.show_task_pattern = //
  rake.load_rakefile
  rake.display_tasks_and_comments
end

def vim_configuration vim_dir
  Dir.chdir vim_dir
  rake = Rake::Application.new
  Rake.application = rake
  rake.init
  rake.load_rakefile
  rake[:vim_install].invoke
end

def everything
  puts "  Starting all.. "
  puts ""
  puts "  ==== Vim ===="
  Rake::Task['install:vim'].invoke
end
