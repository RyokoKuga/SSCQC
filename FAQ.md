# FAQ

よくある質問を掲載しています。今後の版で訂正・改善予定です。

## P.17: GAMESS(US)インストール時のMS-MPIの導入

GAMESS(US)の導入について、Windowsユーザーは予めMS-MPIの導入を行うようにしてください。標準でMPIがインストールされていないPCの場合、MoCalc2012でエラーが出力されます。MPIの導入方法は、Chapter6(P74)に記載のように、Windows 64bit 版(Ver. Aug 18, 2016)の場合、gamess-64フォルダのMS-MPIにある「MSMpiSetup.exe」をインストールします。  

インストール時にエラーが出る場合は、以下から「msmpisdk.msi」を入手して試してみてください。  

[Microsoft MPI v10.0](https://www.microsoft.com/en-us/download/details.aspx?id=57467)

その他にご不明な点や、エラーなどで動作しない場合は、ご遠慮無くお問い合わせください。  

## P.19: 他のバージョンのGAMESS(US)とMoCalc2012との連携

本書では「Ver. Aug 18, 2016」の使用を推奨しています。もし、最近の「Ver. June 30, 2019 R1」を使用したい場合は、MoCalc2012(ver4.2.0.3)と連携するのに少し工夫が必要です。  
例えば、「gamess-64-2019-R1-Patch-1-pgiblas.msi」をダウンロードしたら、通常通りインストーラーの指示に従ってインストールしてください。インストールが終了するとREADMEのPDFが開くので、それの指示に従って並列計算用のMS-MPIを導入します。  

MS-MPIはインストールしたフォルダの「gamess-64\MS-MPI\Version 10.0.12498.5\msmpisetup.exe」にあります。インストール時にエラーが出る場合は、以下から「msmpisdk.msi」を入手して試したみてください。  

[Microsoft MPI v10.0](https://www.microsoft.com/en-us/download/details.aspx?id=57467)  

インストールしたフォルダのWindows-Command-Promptを開いて、一度Enterキーを押して 「create-parameters.bat 」と入力して Enter を押します。これで「 rungms.gms 」というファイルが作成されれば導入は完了です。

本体の実行ファイル名「gamess.2019.R1.P1.pgiblas.exe」のままで、MoCalc2012と連携させるとエラーが発生します。そこで、「gamess.2019-R1-P1.pgiblas.exe」とファイル名を変更してください。あとは、通常通りMoCalc2012のメイン画面のOptions>Settingsから実行ファイルのある場所を指定すれば使用できるようになります。

「June 30, 2020 R1 」以降のバージョンは、MoCalc2012(ver4.2.0.3)と上手く連携・実行できないようなので、推奨しません。  

## P.21: MaSKがダウンロードできない

現在、サイトのドメイン期限が切れてダウンロードできない状況が確認されています。本書で学習をする上で、MaSKの使用は必須ではございません。しかし、MaSKを使って説明している箇所がいくつかありますので、以下の特設ページにて、MoCalc2012を使った方法を記載し補足しております。  
[2023年以降に本書をご購入された方へ](https://github.com/RyokoKuga/SSCQC/blob/master/Af2023.md)  

## P.27: MoCalc2012で計算が実行できない

本書の手順に従っても「Error: No GAMESS/Firefly result file found! 」と表示されて、計算が実行されない場合は、初期設定や入力ファイルで指定したディレクトリ名に日本語やスペース、特殊文字などが含まれていないか確認してください。  
また、Windowsのユーザー名に日本語やスペース、特殊文字が含まれる場合もエラーが発生する場合があります。ユーザー名を英数字などに変更してみてください。MoCalc2012に限らず、海外のソフトウエアではよくあるエラーです。  

もしも、問題が解消されない場合は、MoCalc2012の以下のバージョン(32bit版)を試してみてください。  

[MoCalc2012-setup3141-win32.exe](https://sourceforge.net/projects/mocalc2012/files/)

## P.35: MoCalc2012のJSmol起動時に読込みエラーが発生する

最近のほとんどのブラウザは、アップデートによりローカルディスク内のファイルへのアクセスが制限されている場合があります。設定を変更してください。設定方法は、[JSmol公式のトラブルシューティング](http://wiki.jmol.org/index.php/Troubleshooting/Local_Files)を参考にしてください。Firefoxが設定の変更が一番簡単なのでおすすめです。  

Chapter16-2(P.241): スタンドアローン版のJSmolでエラーが発生する場合も、ブラウザの設定の変更を検討してみてください。

## P.39: MacMolPltの使用について
MacMolPltは、GAMESS(US)用に開発されているので、Fireflyについては正式にサポートされていません。そのため、Fireflyの出力ファイルを読み込むと、解釈の違いによって一部不具合が生じるようです。  

確認されている症状としては、  
- 構造最適化計算では、初期構造しか表示されない  
- 分子軌道の可視化の際(Subwindow>Surfaces)、本来と異なる出力ファイルのデータを参照してしまう  

などです。  

Fireflyをお使いの場合は、なるべくMacMolPltの使用を避け、他のGUIを使用するようにしてください。  

## P.40: JSmolで出力ファイルが読み込めない

サーバー上のJSmolの構成変更により、TypeErrorが発生するようです。URLにアクセスできない場合や、上記のエラーが発生する場合は、Chapter16-2(P.241)のスタンドアローン版のJSmolを使用してください。

## P.72: メモリ不足に関するエラーが出力される

本書で使用しているGAMESS(US)Ver. Aug 18, 2016ではなく、最近のver.2019-R1-path1などをご使用の場合、デフォルト設定ではメモリ不足に関するエラーが発生します。 

出力ファイルには、例えば「NOT ENOUGH MEMORY～」などが印字されます。  

本書のサンプルファイル「Acetophenon.inp」に「**$SYSTEM MWORDS=125 $END**」を追加し、計算を実行してください(メモリの指定方法は、本書のP89に記載しております)。  

## P.74: Fireflyの並列計算ができない

Windowsユーザーは、以下の方法を試してみてください(スタンドアロンのSMP/マルチコアシステムによる並列計算)。  

Fireflyのフォルダ内にbindingsというフォルダがあります。bindingsフォルダ内の「mpibind.nt-mpich-smp.dll」をFirefly実行ファイル(exe)と同じ階層へコピーしてください。最後に、コピーした「mpibind.nt-mpich-smp.dll」を「mpibind.dll」にリネームし、Firefly実行ファイルと同じ階層にある同名ファイルと置き換えてください。  

詳細は、[公式のインフォメーション](http://classic.chem.msu.su/gran/gamess/bindings.html)を参照してください。

## P.83: MaSKで分子が正常に描画できない

MaSKは、出力ファイルの最初の行に5行以上不要な段落が存在すると分子座標を正常に描画できない不具合があります。  
例えば、以下のような情報が記載されている場合がそうです(xxxxxは実行環境によって記載が異なります)。  

Grand Master is running on host xxxxx  
rank #     1 is running on host xxxxx  
rank #     2 is running on host xxxxx  
rank #     3 is running on host xxxxx  
rank #     4 is running on host xxxxx  
rank #     5 is running on host xxxxx  

これは、Fieflyの実行環境によって出力内容が異なのが原因です。  
この場合、該当行を削除することで正常に分子座標を表示することができます。  

## P.103: フロンティア軌道の可視化

MoCalc2012を使った方法について補足します。MoCalc2012で計算が終了した状態、または、Outputファイルを読み込んだ状態から解説します。ここでは、「SampleData/Chapter08/HF_6-31G(d)/Phenol.out」を使用します。

1)MoCalc2012のメイン画面から[Orbitals Surfaces]ボタンをクリックします。  
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb001.png" width="600px">  

2)サブウインドウが表示されるので[Structure, Orbitals]をクリックします。  
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb002.png" width="200px">  
ブラウザ(JSmol)で構造が表示されます。右クリックメニューから[面>分子軌道>#33A-0.3092]を選択します。  
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb003.png" width="600px">  
HOMOが可視化された様子は下図の通りです。  
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb004.png" width="600px">  

3)電子に占有されている最もエネルギーの高い分子軌道(HOMO)の準位は、Outputファイルを開き「NUMBER OF OCCUPIED ORBITALS (ALPHA)」を検索すると見つかります。ここで、25番目の軌道がHOMOであることが分かります。
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb005.png" width="600px">  
P115に記載されてる方法で、25番目の軌道に関する情報を参照すると、軌道のエネルギーが-0.3092Hartreesであることが分かります。先ほど右クリックメニューから選択した[面>分子軌道>#33A-0.3092]の[-0.3092]は、このエネルギー値のことを表します。
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb006.png" width="600px">  
JSmolの右クリックメニュー[面>分子軌道>#番号]で表示される番号(ここでは#33)は、Outputファイルに記載されているHOMOの軌道番号と一致しないので注意しましょう。これは、JSmolの仕様上の問題です。 [面>分子軌道>]の#1~8を確認するとわかるようにNaN(非数)と必要ない箇所も読み込まれるのが原因です。つまり#33から必要ない#8の数字を引いた数字25がHOMOの軌道番号と一致する事が分かります。  
<img src="https://github.com/RyokoKuga/SSCQC/blob/master/Image/orb007.png" width="600px">   

## P.169: GAMESS(US)のRUNTYP=SURFACEについて

本書では説明が不足していましたが、FireflyのRSURFACEは各構造で構造最適化を行うのに対して、GAMESSのSURFACEでは構造最適化は行われない仕様になっています。   
ですので、P169記載のFireflyの入力ファイルの内容をキーワードを変えてGMESSで実行しても上手くいきません。GAMESSのSURFACEは、例えば、単原子間の距離を変更させて相互作用エネルギーの変化を確認する場合など、各構造で最適化が必要でない場合に適しています。  

## P.182: MoCalc2012のIRC計算について

遷移状態用の座標ファイル(molファイルなど)をMoCalc2012で読み込み、Job Type「IRC Calculation」で計算を実行してください。遷移状態計算用の入力ファイル（RUNTYP=SADPOINT）を読み込んで実行すると、単に遷移状態計が実行されるだけなので注意してください。  

書籍では、「続けてIRC計算をおこないますか？」という意訳を使っていますが、実際は、P.182中程の画像のように「2nd part of GAMESS/Firefly calculation ready. Results of 1st run will be overwritten. Proceed with calculation?」（GAMESS/Fireflyの次の計算準備が整いました。はじめの計算結果は上書きされます。計算を続行しますか？）というダイアログ画面で、「はい」又は「いいえ」を選択します。  

このダイアログウインドウが表示されない場合は、遷移状態計算が正常に終了していない可能性があります。分子座標及び入力ファイルのキーワードを見直してみてください。  
