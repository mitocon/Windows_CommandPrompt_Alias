# Windows コマンドプロンプトのエイリアス設定例
## 概要
コマンドプロンプト(cmd)で、エイリアスで設定したコマンドを実行できるようになります。  
(例) コマンドプロンプトで```pj```と打つと、 D:¥#任意のパス# をVSCodeで開く… などの動作が可能。
```
C:¥Users¥mito-con
> pj

（→ D:¥#任意のパス# をVSCodeで開く）
```

## 設定方法
1. 任意の場所にmacros.txtを作成します。（Shift JISで保存してください）  
   ※今回は ```D:¥Users¥mito-con¥cmd¥macros.txt``` に作成します。
1. 実行するcmd.exeのショートカットのプロパティを開きます。  
   スタートメニューで「cmd」と打つと、コマンドプロンプトが出るので、  
   右クリック「ファイルの場所を開く」→ショートカットに対して右クリック「プロパティ」。
1. 「ショートカット」タブの「リンク先」に、以下の```/k```より後を追記します。  
   ```%windir%system32¥cmd.exe /k doskey /macrofile=D:¥Users¥mito-con¥cmd¥macros.txt```
   D:¥ 以下は macros.txt のパスを指定してください。

これでエイリアスが登録できました。

注意：タスクバーなどにcmdのショートカットを配置している場合は、今回設定したショートカットに置き換えてください。  
　　　置き換えないと設定したエイリアスが反映されません。

## トラブルシューティング
- Q. エイリアスを設定したのに反映されない。
  - ショートカットに対して設定しましたか？  
    cmd.exeに対して直接設定するのではなく、ショートカットに設定します。  
    タスクバーにショートカットがある場合、タスクバーの既存のショートカットを削除した後、エイリアスを設定したショートカットを再配置してください。

- Q. 日本語名のフォルダやファイルが開けない。実行できない。
  - エイリアスファイルの文字コードはShift JISになっていますか？
    UTF-8の場合は読み取れない場合があるようです。

## 参考
Qiita [Windowsのコマンドプロンプトでaliasを設定する (cmderの設定含む)](https://qiita.com/little_hand_s/items/91d6bcb680eba10da835)
