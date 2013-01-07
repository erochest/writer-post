# A sample Guardfile
# More info at https://github.com/guard/guard#readme

# Add files and commands to this file, like the example:
#   watch(%r{file/path}) { `command(s)` }
#
guard 'shell' do
  watch(/(.*).lhs/) do |m|
    `pandoc -f markdown+lhs -t html5+lhs #{m[0]} > #{m[1]}.html`
    `cabal build`
    `./dist/build/writer-post/writer-post`
  end

  watch(/(.*).cabal/) do |m|
    `cabal configure`
  end
end
