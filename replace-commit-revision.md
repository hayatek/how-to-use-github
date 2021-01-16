# コミット履歴の内容を一括変換

1. 以下を実行
>  git filter-branch -f --env-filter "GIT_AUTHOR_NAME='名前'; GIT_AUTHOR_EMAIL='メールアドレス'; GIT_COMMITTER_NAME='名前'; GIT_COMMITTER_EMAIL='メールアドレス';" HEAD
2. git push or git push -f

コミットIDを指定する場合は以下を実行
>git filter-branch --env-filter '
if [ $GIT_COMMIT = "<commit_id>" ]
then
    export GIT_AUTHOR_NAME="名前"
    export GIT_AUTHOR_EMAIL="メールアドレス"
    export GIT_COMMITTER_NAME="名前"
    export GIT_COMMITTER_EMAIL="メールアドレス"
fi'
