.. _exp-page-structure:

適切なページ構造、マークアップとスクリーン・リーダーを用いた効率的な情報アクセス
----------------------------------------------------------------------------------

ページを開いたり新たなページに遷移した直後、多くのスクリーン・リーダーでは自動的に ``title`` 要素の内用を読み上げます。
また、複数のウィンドウやタブを切り替えながら利用している場合、 ``title`` 要素の中身で目的のウィンドウ/タブかを判断します。
したがって、 ``title`` 要素の内用をそのページを特定できるものにすることが求められます。

目的のページにたどり着いたら、ユーザーはまずそのページに自分が求めている情報や機能があるかどうかを判断する場合が多いでしょう。
画面全体を一度に見ることができる場合、この判断は容易ですが、スクリーン・リーダーを使っているユーザーの多くは、ある程度ページの中身を読まないと判断することが困難です。
多くのスクリーン・リーダーには複数のARIA landmark roleの間を移動する機能がありますので、ページの主立った構成要素にARIA landmark roleが指定されていれば、ユーザーは斜め読みのような形でページ全体の構成を把握することができ、また目的の情報が掲載されているかどうかの判断に役立てることができます。

特に長いページにおいてより効率的な斜め読みを可能にするためには、 ``h?`` 要素を用いてページ内に複数の見出しを配置することが有効です。
ただ、コンテンツの量や性質によっては、複数の見出しを配置することが必ずしも適当ではない場合もありますから、積極的な ``h?`` 要素の利用は[SHOULD]でのみ求められています。

複数の見出しがあるページの場合、ページ内の情報の構造に合わせて適切な見出しレベルを用いることが重要です。
たとえば、記事のタイトルは ``h1`` 要素、記事中の小見出しは ``h2`` 要素、さらに仮想の見出しは ``h3`` 要素を用いる、といった具合です。

実際にコンテンツを読み始めるとき、ナビゲーションのリンクなどを飛ばして本文の先頭に移動することになります。
本文部分が ``main`` 要素でマークアップされていたり、本文の先頭の見出しが ``h1`` でマークアップされていれば、スクリーン・リーダーの機能を活用して本文の先頭に容易に移動することが可能です。

そしてさらに読み進めていくに当たっては、スクリーン・リーダーはDOM treeに出現する順序 (≒HTMLソースの記述順序) に従って読み上げます。
そのため、画面上ではCSSによって隣接した位置に表示されている要素であっても、DOM tree上で離れた位置にあれば、画面表示と読み上げの順序が異なることになります。
当該要素が隣接していることで、その意味が伝わりやすいような場合は特に、DOM tree上の順序が適切になっていることが重要です。

関連ガイドライン
~~~~~~~~~~~~~~~~~~

*  ページ: :ref:`page-structure`
