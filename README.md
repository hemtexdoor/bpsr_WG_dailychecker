☆スタレゾ・チェックリストくん☆
・概要
ブループロトコル・スターレゾナンスにおいて、日課・週課漏れを防ぐためのインタラクティブチェックリストです。
チェックリスト自体は既出のモノがありますが、使い勝手が個人的に気に食わなかったのでこのツールを作成しました。

・えでぃたー
ふみづきしでん(id:Hemtexdoor/ guild:wolfgang)

・グローバル変数
　・最大所持数関連
　　・ボス鍵・精鋭鍵
　　・ホーム依頼
　　・フォーカス
　　・友好度
　　　・アシスト　1000pt
　　　・イベント　1000pt
   ※jsonの構成
max_para = 
{ boss :6,
  elite:6,
  home :6,
  focus:2000,
  frendry_assist:1000,
  frendry_event :1000,
}
　・増加分
　　・ボス鍵・精鋭鍵
　　・ホーム依頼
　　・フォーカス
　  ※jsonの構成
add_para =
{ boss :2,
  elite:2,
  home :2,
  focus:400,
}
　・現在の数
　　・ボス鍵・精鋭鍵
　　・ホーム依頼
　　・フォーカス
   ※jsonの構成
current_para = 
{ flag_init:0,
  boss :0,
  elite:0,
  home :0,
  focus:0,
}//Localstorageにセーブ・ロードして更新される
current_para_ini =
{ flag_init:0,
  boss :0,
  elite:0,
  home :0,
  focus:0,
}//初期化する際のjsonデータ

・データ保存場所
　・LocalStorageを使って保存
　・キーはjsonDataの頭に`key_`を付ける


・機能
　・初回ロード

　・セーブ：パラメータ弄った時に変更済みのFlagを立ててから自動上書き
　・ロード：読み込み時にlocalstorageから現在の値を読み込み
　・日リセット
　　・日タスクをfalseに上書き
　　・鍵+2
　　　　・IF(最大所持－増加分<所持数) 溢れアラート
　　　　・IF(最大所持－増加分<所持数)　上限に上書き
　　・ホーム依頼+3
　　　　・IF(最大所持－増加分<所持数) 溢れアラート
　　　　・IF(最大所持－増加分<所持数)　上限に上書き
　　・フォーカス+200
　　　　・IF(最大所持－増加分<所持数) 溢れアラート
　　　　・IF(最大所持－増加分<所持数)　上限に上書き
　・週リセット
　　・日リセット
　　・週リセット
　　　・週タスクをfalseに上書き
　・完全リセット
　　・iniで上書き
　　・フォームをロードする
・デイリー
　・[checkbox]　神秘ストアチェック
　・[checkbox]　ギルド出席・輸送　
　・[checkbox]　不安定
　・[-][number][+] フォーカス所持数　　初期値=増加数
　・[-][number][+] ホーム依頼所持数　　初期値=増加数
　・[-][number][+] ボス鍵　　所持数　　初期値=増加数
　・[-][number][+] 精鋭鍵　　所持数　　初期値=増加数
　・[checkbox]　開拓局の依頼
　・[checkbox]　ワールドレイド
　・[checkbox]　活躍度
　・[checkbox]　友好度(80+5)*2程度取得する

・ウィークリー
　・[checkbox]　今週解放される要素の確認
　・[checkbox]　開拓者褒賞の受取
　・[checkbox]　補償ショップで買い物
　・[checkbox]　シーズンパスストアで買い物
　・[checkbox]　GCショップで買い物
　・[checkbox]　名声ショップで買い物
　・[checkbox]　ギルド売店で買い物
　・[number][+] 友好度　　所持数　　初期値=0
　・[checkbox]　クラフトタスク(S1・必要に応じて)
　・[checkbox]　改鋳石周回
　・[checkbox]　浮島レイド－イージー
　・[checkbox]　浮島レイド－ハード
　・[checkbox]　浮島レイド－ナイトメア
　・[checkbox]　遺跡の更新チェック
　・[checkbox]　金曜のギルドダンス
　・[checkbox]　金曜のギルドハント
　・[checkbox]　土曜のギルドハント
　・[checkbox]　日曜のギルドハント

・備考
遺跡は2週間更新ですが、更新が長いので半分の1週間でもれなく確認をすることにしています
