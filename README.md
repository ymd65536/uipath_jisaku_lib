# uipath_jisaku_lib
UiPath 自作ライブラリのリポジトリ

## セレクタに関するメモ

属性名にそれぞれ意味がある。

``` xml
<wnd app='iexplore.exe' cls='#32770' title='Windows Internet Explorer' />
<wnd ctrlid='6' title='はい(&amp;Y)' />

<wnd app='iexplore.exe' cls='#32770' title='Windows Internet Explorer' />
<wnd ctrlid='6' title='はい(&amp;Y)' />
```

app ： アプリケーションを起動しているプログラム名  
cls ： Automation SpyやAutoItで取得できるウィンドウクラス名  
title ： そのウィンドウのウィンドウヘッダ(HTMLのHEADタグにあるtitleに相当) 
ctrlid ：ウィンドウ上にあるUIの番号  
title： ctrlidに関連するUIのキャプション名  

また、WebページからのメッセージとWindow Internet Explorerに使われるセレクタはほぼ同じ

``` xml
<wnd app='iexplore.exe' cls='#32770' title='Web ページからのメッセージ' />
<wnd ctrlid='20' />

<wnd app='iexplore.exe' cls='#32770' title='Web ページからのメッセージ' />
<wnd ctrlid='1' title='OK' />
```

Webページからのメッセージのclsは#32770で固定
複数回取得を試みたが同じだった。

他、HTMLタグを捉えたときのセレクター

``` xml

<html htmlwindowname='XXX' title='メインメニュー' />
<webctrl name='test' tag='INPUT' />

<html htmlwindowname='XXX' title='ログアウト' />
<webctrl tag='INPUT' type='submit' />

```

htmlwindowname：ブラウザで表示しているタイトル名とは別のウィンドウ識別子  
title：そのウィンドウのウィンドウヘッダ(HTMLのHEADタグにあるtitleに相当)  
webctrl name='test' tag='INPUT'：属性名nameに属性値testがついているinputタグ  
webctrl tag='INPUT' type='submit'：submit 属性をもつinputタグ


