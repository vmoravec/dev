namespace :install do
  desc "Vim configuration"
  task :vim do
    vim_configuration 'vim'
  end
end

desc "Default task"
task :default do
  puts "Run 'rake -T' to get all options for configuration"
end

def vim_configuration vim_dir
  Dir.chdir vim_dir
  rake = Rake::Application.new
  Rake.application = rake
  rake.init vim_dir
  rake.load_rakefile
  rake[:vim_install].invoke
end
