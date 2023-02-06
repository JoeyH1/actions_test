require 'rake'

task :clean => %w[clean_tasks:html clean_tasks:pdf]
task :build => %w[build_tasks:both]

namespace :clean_tasks do
  task :html do
    html_dir = "#{__dir__}/html/*"
    FileUtils.rm_r(FileList[html_dir]) unless FileList[html_dir].empty?
    puts "HTML Directory Cleaned"
  end

  task :pdf do
    pdf_dir = "#{__dir__}/pdf/*"
    FileUtils.rm_r(FileList[pdf_dir]) unless FileList[pdf_dir].empty?
    puts "PDF Directory Cleaned"
  end
end

namespace :build_tasks do
  task :html do
    ruby "#{__dir__}/lib/document_generator.rb nil nil html"
    puts "HTML Documents Generated"
  end

  task :pdf do
    ruby "#{__dir__}/lib/document_generator.rb nil nil pdf"
    puts "PDF Documents Generated"
  end

  task :both do
    ruby "#{__dir__}/lib/document_generator.rb nil nil both"
    puts "HTML & PDF Documents Generated"
  end
end

namespace :action_test do
  task :puts_hello_world do
    ruby "puts hello world"
  end
end
