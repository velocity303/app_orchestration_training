# This rakefile contains tasks for automating the setup of the debugging kit.
namespace :setup do
  desc 'Install requirements into a global Vagrant setup'
  task :standard do
    %w[oscar sahara].each do |plugin|
      Kernel.system 'vagrant', 'plugin', 'install', plugin
    end
  end

  desc 'Install requirements into a local sandbox managed by Bundler'
  task :sandboxed do
    Kernel.system 'bundle', 'install', '--binstubs', '--path=vendor'
  end
end