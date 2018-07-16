require 'bundler/setup'

namespace :user_create do
  SHELL = '/usr/bin/zsh'
  desc 'root_user_create'
  task :root do
    print 'create_username?:'
    name = STDIN.gets.chomp
    cmd = "sudo useradd -s #{SHELL} -G wheel,cy-world -m #{name}"
    begin
      exec(cmd)
      puts "#{name}を作成しました"
      rescue
      puts 'error'
    end
  end
  
  desc 'cy-world_user_create'
  task :user do
    print 'create_username?:'
    name = STDIN.gets.chomp
    cmd = "sudo useradd -s #{SHELL} -G cy-world -m #{name}"
    begin
      result = exec(cmd)
      rescue
      puts 'error'
    end
  end
  
end

desc 'user_delete'
task :user_del do
  puts "=" * 20
  users = `cat /etc/passwd|sed -e 's/:.*//g'`
  puts users
  puts "=" * 20
  print 'delete_username?:'
  name = STDIN.gets.chomp
  cmd = "sudo userdel -r #{name}"
  print "#{name}を削除しても宜しいですか？[y/n]:"
  res = STDIN.gets.chomp
  if res == "y" then
    begin
      exec(cmd)
      puth "#{name}を削除しました"
      rescue
      puts 'error'
    end
  elsif res == "n"
    puts "処理を中断します。"
    exit!
  end
end
