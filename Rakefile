namespace :book do
  desc 'prepare build'
  task :prebuild do
    Dir.mkdir 'images' unless Dir.exists? 'images'
    Dir.glob("book/*/images/*").each do |image|
      FileUtils.copy(image, "images/" + File.basename(image))
    end
  end

  desc 'build basic html book'
  task :build_html => :prebuild do
    puts "Converting to HTML..."
    `bundle exec asciidoctor -r asciidoctor-diagram seia.asc -o 智眼用户安装文档.html`
    puts " -- HTML output at 智眼用户安装文档.html"
  end
end
