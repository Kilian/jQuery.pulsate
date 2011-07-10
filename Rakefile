require 'rubygems'

desc 'Packages Grafico'
task :package => [:require_compiler] do
  sources  = ['pulsate']
  packaged = File.join(File.dirname(__FILE__), 'jquery.pulsate.min.js')
  unpackagedsize = 0

  file = File.join(File.dirname(__FILE__), "jquery.pulsate.js")
  unpackagedsize += File.size(file)
  contents = File.read(file)

  File.open(packaged, "w") do |f|
    f.write Closure::Compiler.new.compile(contents)
  end
end

task :require_compiler do
  begin
    require 'closure-compiler'
  rescue LoadError
    puts "Install closure-compiler:"
    puts "sudo gem install closure-compiler --source http://gemcutter.org"
    abort
  end
end

