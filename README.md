# 概要
Linuxサーバーにてユーザーを自動生成してくれるツール

# 使い方
[gen@gen-server](master) $ be rake Rakefile -T
rake user_create:root  # root_user_create
rake user_create:user  # cy-world_user_create
rake user_del          # user_delete