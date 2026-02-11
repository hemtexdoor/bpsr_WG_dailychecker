☆スタレゾ・チェックリストくん☆<br>
・概要<br>
ブループロトコル・スターレゾナンスにおいて、日課・週課漏れを防ぐためのインタラクティブチェックリストです。<br>
チェックリスト自体は既出のモノがありますが、使い勝手が個人的に気に食わなかったのでこのツールを作成しました。<br>
<br>
・えでぃたー<br>
ふみづきしでん(id:Hemtexdoor/ guild:wolfgang)<br>
<br>
・グローバル変数<br>
　・最大所持数関連<br>
　　・ボス鍵・精鋭鍵<br>
　　・ホーム依頼<br>
　　・フォーカス<br>
　　・友好度<br>
　　　・アシスト　1000pt<br>
　　　・イベント　1000pt<br>
   ※jsonの構成<br>
max_para = <br>
{ boss :6,<br>
  elite:6,<br>
  home :6,<br>
  focus:2000,<br>
  frendry_assist:1000,<br>
  frendry_event :1000,<br>
}<br>
　・増加分<br>
　　・ボス鍵・精鋭鍵<br>
　　・ホーム依頼<br>
　　・フォーカス<br>
　  ※jsonの構成<br>
add_para =<br>
{ boss :2,<br>
  elite:2,<br>
  home :2,<br>
  focus:400,<br>
}<br>
　・現在の数<br>
　　・ボス鍵・精鋭鍵<br>
　　・ホーム依頼<br>
　　・フォーカス<br>
   ※jsonの構成<br>
current_para = <br>
{ flag_init:0,<br>
  boss :0,<br>
  elite:0,<br>
  home :0,<br>
  focus:0,<br>
}//Localstorageにセーブ・ロードして更新される<br>
current_para_ini =<br>
{ flag_init:0,<br>
  boss :0,<br>
  elite:0,<br>
  home :0,<br>
  focus:0,<br>
}//初期化する際のjsonデータ<br>
<br>
・データ保存場所<br>
　・LocalStorageを使って保存<br>
　・キーはjsonDataの頭に`key_`を付ける<br>
<br>
<br>
・機能<br>
　・初回ロード<br>
<br>
　・セーブ：パラメータ弄った時に変更済みのFlagを立ててから自動上書き<br>
　・ロード：読み込み時にlocalstorageから現在の値を読み込み<br>
　・日リセット<br>
　　・日タスクをfalseに上書き<br>
　　・鍵+2<br>
　　　　・IF(最大所持－増加分<所持数) 溢れアラート<br>
　　　　・IF(最大所持－増加分<所持数)　上限に上書き<br>
　　・ホーム依頼+3<br>
　　　　・IF(最大所持－増加分<所持数) 溢れアラート<br>
　　　　・IF(最大所持－増加分<所持数)　上限に上書き<br>
　　・フォーカス+200<br>
　　　　・IF(最大所持－増加分<所持数) 溢れアラート<br>
　　　　・IF(最大所持－増加分<所持数)　上限に上書き<br>
　・週リセット<br>
　　・日リセット<br>
　　・週リセット<br>
　　　・週タスクをfalseに上書き<br>
　・完全リセット<br>
　　・iniで上書き<br>
　　・フォームをロードする<br>
・デイリー<br>
　・[checkbox]　神秘ストアチェック<br>
　・[checkbox]　ギルド出席・輸送　<br>
　・[checkbox]　不安定<br>
　・[-][number][+] フォーカス所持数　　初期値=増加数<br>
　・[-][number][+] ホーム依頼所持数　　初期値=増加数<br>
　・[-][number][+] ボス鍵　　所持数　　初期値=増加数<br>
　・[-][number][+] 精鋭鍵　　所持数　　初期値=増加数<br>
　・[checkbox]　開拓局の依頼<br>
　・[checkbox]　ワールドレイド<br>
　・[checkbox]　活躍度<br>
　・[checkbox]　友好度(80+5)*2程度取得する<br>
<br>
・ウィークリー
　・[checkbox]　今週解放される要素の確認<br>
　・[checkbox]　開拓者褒賞の受取<br>
　・[checkbox]　補償ショップで買い物<br>
　・[checkbox]　シーズンパスストアで買い物<br>
　・[checkbox]　GCショップで買い物<br>
　・[checkbox]　名声ショップで買い物<br>
　・[checkbox]　ギルド売店で買い物<br>
　・[number][+] 友好度　　所持数　　初期値=0<br>
　・[checkbox]　クラフトタスク(S1・必要に応じて)<br>
　・[checkbox]　改鋳石周回<br>
　・[checkbox]　浮島レイド－イージー<br>
　・[checkbox]　浮島レイド－ハード<br>
　・[checkbox]　浮島レイド－ナイトメア<br>
　・[checkbox]　遺跡の更新チェック<br>
　・[checkbox]　金曜のギルドダンス<br>
　・[checkbox]　金曜のギルドハント<br>
　・[checkbox]　土曜のギルドハント<br>
　・[checkbox]　日曜のギルドハント<br>
<br>
・備考<br>
遺跡は2週間更新ですが、更新が長いので半分の1週間でもれなく確認をすることにしています<br>
