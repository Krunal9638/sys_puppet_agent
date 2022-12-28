source ENV['GEM_SOURCE'] || 'https://rubygems.org'

gem 'xoom_litmus_spec_helper', '~> 0.2.9'

#def location_for(place_or_version, fake_version = nil)
  git_url_regex = %r{\A(?<url>(https?|git)[:@][^#]*)(#(?<branch>.*))?}
  file_url_regex = %r{\Afile:\/\/(?<path>.*)}

  if place_or_version && (git_url = place_or_version.match(git_url_regex))
    [fake_version, { git: git_url[:url], branch: git_url[:branch], require: false }].compact
  elsif place_or_version && (file_url = place_or_version.match(file_url_regex))
    ['>= 0', { path: File.expand_path(file_url[:path]), require: false }]
  else
    [place_or_version, { require: false }]
  end
#end

#ruby_version_segments = Gem::Version.new(RUBY_VERSION.dup).segments
#minor_version = ruby_version_segments[0..1].join('.')

