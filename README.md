## ハンバーガーメニュー作成

[ハンバーガーメニュー](https://vuetifyjs.com/ja/components/app-bars/)
[参考](https://yacchi-engineer.com/?p=1010)

・v-navigation-drawer, v-app-bar, v-footerの3つのコンポーネントが必須
「v-navigation-drawer」は、サイドナビゲーションを生成する。
・Vuetifyのコンポーネントは必ずv-appタグで囲む必要がある。
・サイドメニューは、
・ハンバーガーメニューは「v-app-bar-nav-icon」タグとして準備されている。
・「:clipped-left="clipped"」のclippedはboolean。
　clippedはナビゲーションバーの下に配置する設定。
　オン、オフの切り替え。clippedはprops。
「v-navigation-drawer」にclippedを、「v-app-bar」にclipped-leftを設置。
 データ定義する際は、dataプロパティを使用し、return部分にオブジェクト形式でデータ定義する。
・サイドバーの中には、v-listでメニューを表示
・fixedは、position:fixedのスタイルが効き、サイドメニューが画面左側いっぱいに表示することが可能。
・temporaryはサイドメニューがヘッダーから隠れるのを防ぐ
・サイドメニューの並び、
　<v-list>
　<v-list-item-group>
　<v-list-item>
　<v-list-item-title>
・denseは、margin設定を自動調整してくれる
・「v-list-item-action」は、「v-list-item」に配置し、表示位置に表す。
・ハンバーガーメニューを右から表示したい場合は、v-navigation-drawerで、rightを加える。
