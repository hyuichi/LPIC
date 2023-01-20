
# LPIC Day.1
## コマンドライン操作
### cd
cd : Change Directory  
前提 ： 現在位置 "/home/hyuichi"

 | 相対パス | 絶対パス |
 |---|:---:|---:|
 | `$cd ..` | `/home` |
 | `$cd ../../opt/` | `/opt` |
 | `$cd LPIC` | `/home/hyuichi/LPIC` |

 `cd` = `cd ~` = `cd ~username` = `cd /home/username`

 ファイルシステム内を移動するコマンド。  
 ホームディレクトリーの指定も覚えておこう。  
 アクセス権限がないところには移動不可。

  `root`のホームは`/root`。


### pwd
pwd : Print Working Directory

現在ファイルシステムのどこにいるか確認するコマンド。


### date
時間・日付の確認・取得・修正などするコマンド。


```bash
# 現在の日時を表示
$ date
Fri Jan 20 05:41:43 UTC 2023

# フォーマットは + で始まる書式で指定
$ date "+%Y%m%d-%H%M%S"
20230120-054218

# 出力フォーマット指定サンプル
$ date "+%Y/%m/%d %H:%M:%S"
2023/01/20 05:40:18
```

#### オプション

##### `-d 日時`, `--date 日時`

日時を指定

```bash
# 24時間後の日時を表示
$ date -d tomorrow
Sat Jan 21 05:37:45 UTC 2023

# 30日後の日付を表示
$ date "+%Y/%m/%d" -d "30 days"
2023/02/19
```
###### SAMPLE
`"2 hours ago"`  
`"day"` = `"tommorow"`  
`"-1 day"` = `"-1 day ago"` = `"yesterday"`

##### `-u`, `--utc`, `--universal`

UTCで表示

```bash
# 現在の日時をUTCで表示
$ date -u
Fri Jan 20 05:41:01 UTC 2023
```

##### `-r ファイルパス`, `--reference ファイルパス`

ファイルの更新日時を表示

##### `-s 日時`

サーバ日時の変更

```bash
#OSの現在時間修正
$ sudo date -s "2023/01/01 00:00:00"
```
#### 日付フォーマット

フォーマット|説明|値
:---:|:----:|---:
`%A`|曜日|Sunday
`%B`|月|January
`%H`|時|00~23
`%M`|分|00~59

###### SAMPLE
```bash
# -u
$ date -u
Fri Jan 20 06:08:53 UTC 2023

# %c 日時
$ date "+%c"
Fri 20 Jan 2023 06:04:19 AM UTC

# %x 日付
$ date "+%x"
01/20/2023

# %C 日
$ date "+%C"
20
```

参照：hydroculのメモ > コマンドの使い方(Linux) > date コマンド
https://hydrocul.github.io/wiki/commands/date.html

### man
`man` = Manual

```bash
# manコマンドが呼び出すドキュメントの位置
$ find / -name "man" 2>/dev/null
# 2>/dev/null : エラーメッセージを表示しない
/var/cache/man
/usr/bin/man
#/usr/lib/node_modules/npm/man
#/usr/lib/node_modules/npm/node_modules/sshpk/man
/usr/share/man
/usr/share/locale/man
#/usr/share/bash-completion/completions/man
#/usr/local/lib/node_modules/npm/node_modules/cssesc/man
#/usr/local/lib/node_modules/npm/man
/usr/local/share/man
#/usr/local/n/versions/node/18.13.0/share/man
#/usr/local/n/versions/node/18.13.0/lib/node_modules/npm/man
#/usr/local/n/versions/node/18.13.0/lib/node_modules/npm/node_modules/cssesc/man
```

### history
### alias
### su
### ファイル: /usr/share/man

