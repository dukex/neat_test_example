require 'bundler'

Bundler.require

task :test, :sass_file do |t, args|
  sass_file = args[:sass_file]
  bourbon_lib = args[:bourbon_lib] or "../neat/app/assets/stylesheets/bourbon/lib/bourbon.rb"

  system("sass -r #{bourbon_lib} #{sass_file}:test.css")
  include CssParser

  parser = CssParser::Parser.new
  parser.load_file!('test.css')
  test(parser, '.omega-default', 'margin-right', '0')
  test(parser, '.omega-table', 'padding-right', '0')
  test(parser, '.omega-default-left', 'margin-left', '0')
  test(parser, '.omega-table-left', 'padding-left', '0')

  test(parser, '.omega-nth-default:nth-child(4n)', 'margin-right', '0')
  test(parser, '.omega-nth-table:nth-child(4n)', 'padding-right', '0')

  test(parser, '.omega-nth-default-left:nth-child(4n)', 'margin-left', '0')
  test(parser, '.omega-nth-table-left:nth-child(4n)', 'padding-left', '0')
end

def test(parser, selector, declaration, value)
  puts
  rules = parser.find_by_selector(selector)
  rules.each do |rule|
    rule_declaration, rule_value = rule.split(":")
    rule_value.gsub!(/;|^ /, "")
    if rule_declaration == declaration and rule_value == value
      puts "passed, #{selector} has #{declaration} equal #{value}"
      return
    end
  end
  puts "expected `#{selector}` with `#{declaration}:#{value}` but failed, got only `#{rules}`"
end
