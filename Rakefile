desc "Update"
task :update do
  src_path = "x-editable-src"
  dist_path = "#{src_path}/dist/bootstrap-editable"

  system("rm -rf #{src_path}")

  system("git clone https://github.com/vitalets/x-editable #{src_path}")
  system("cd #{src_path} && npm install")
  system("cd #{src_path} && grunt build")

  system("cp #{dist_path}/img/clear.png app/assets/images/")
  system("cp #{dist_path}/img/loading.gif app/assets/images/")
  system("cp #{dist_path}/css/bootstrap-editable.css app/assets/stylesheets/bootstrap-editable.scss")
  system("cp #{dist_path}/js/bootstrap-editable.js app/assets/javascripts/")

  fixes

  system("rm -rf x-editable-src")
end

def fixes
  replace_string_in_file("app/assets/stylesheets/bootstrap-editable.scss", "url('../img/loading.gif')", "image-url('loading.gif')")
  replace_string_in_file("app/assets/stylesheets/bootstrap-editable.scss", "url('../img/clear.png')", "image-url('clear.png')")
end

def replace_string_in_file(file, find, replace)
  file_content = File.read(file)

  File.open(file, "w") do |f|
    f.puts file_content.gsub!(find, replace)
  end
end

desc "Build"
task "build" do
  system("gem build bootstrap-x-editable-rails.gemspec")
end
