# FAQ

　よくある質問を掲載しています。今後の版で訂正・改善予定です。

## P.17: GAMESS(US)インストール時のMS-MPIの導入

　GAMESS(US)の導入について、Windowsユーザーは予めMS-MPIの導入を行うようにしてください。標準でMPIがインストールされていないPCの場合、MoCalc2012でエラーが出力されます。
　MPIの導入方法は、Chapter6(P74)に記載のように、Windows 64bit 版(Ver. Aug 18, 2016)の場合、gamess-64フォルダのMS-MPIにある「MSMpiSetup.exe」をインストールします。
　インストール時にエラーが出る場合は、以下から「msmpisdk.msi」を入手して試してみてください。

[Microsoft MPI v10.0](https://www.microsoft.com/en-us/download/details.aspx?id=57467)

　その他にご不明な点や、エラーなどで動作しない場合は、ご遠慮無くお問い合わせください。

## P.35: MoCalc2012のJSmol起動時に読込みエラーが発生する

　最近のほとんどのブラウザは、アップデートによりローカルディスク内のファイルへのアクセスが制限されている場合があります。設定を変更してください。
　設定方法は、[JSmol公式のトラブルシューティング](http://wiki.jmol.org/index.php/Troubleshooting/Local_Files)を参考にしてください。
　Firefoxが設定の変更が一番簡単なのでおすすめです。

　Chapter16-2(P.241): スタンドアローン版のJSmolでエラーが発生する場合も、ブラウザの設定の変更を検討してみてください。

## P.40: JSmolで出力ファイルが読み込めない

　サーバー上のJSmolの構成変更により、TypeErrorが発生するようです。

　URLにアクセスできない場合や、上記のエラーが発生する場合は、Chapter16-2(P.241)のスタンドアローン版のJSmolを使用してください。

## P.74: Fireflyの並列計算ができない

　以下の方法を試してみてください(スタンドアロンのSMP/マルチコアシステムによる並列計算)。
　Fireflyのフォルダ内にbindingsというフォルダがあります。bindingsフォルダ内の「mpibind.nt-mpich-smp.dll」をFirefly実行ファイル(exe)と同じ階層へコピーしてください。
　最後に、コピーした「mpibind.nt-mpich-smp.dll」を「mpibind.dll」にリネームし、Firefly実行ファイルと同じ階層にある同名ファイルと置き換えてください。
　詳細は、[公式のインフォメーション](http://classic.chem.msu.su/gran/gamess/bindings.html)を参照してください。

