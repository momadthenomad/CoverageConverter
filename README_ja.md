Coverage Converter とは？
-------  
MsTestを実行後に出力されるカバレッジファイルを  
XMLファイル形式に変換します。  
JenkinsでカバレッジファイルをEmma形式のレポートファイルに変換する時に  
使用すると便利です。  


Coverage Converter の種類
-------  
<table>
<tr>
  <th>ファイルパス</th>
  <th>.NET Framework</th>
  <th>説明</th>
</tr>
<tr>
  <td>mstest/Binaries/CoverageConverter.exe</td>
  <td>3.5</td>
  <td>
    mstest.exeから作成されたカバレッジファイルを変換出来ます。
  </td>
</tr>
<tr>
  <td>vstest/Binaries/CoverageConverter.exe</td>
  <td>4.5</td>
  <td>
    vstest.console.exeから作成されたカバレッジファイルを変換出来ます。
  </td>
</tr>
</table>


コマンドライン引数
-------
<table>
<tr>
  <th>引数</th>
  <th>説明</th>
</tr>
<tr>
  <td>/in:[ ファイルパス ]</td>
  <td>
    入力対象のファイルパスを指定します。<br />
    入力例：/in:data.coverage
  </td>
</tr>
<tr>
  <td>/out:[ ファイルパス ]</td>
  <td>
    出力対象のファイルパスを指定します。<br />
    入力例：/out:data.xml
  </td>
</tr>
<tr>
  <td>/symbols:[ ディレクトリ ]</td>
  <td>
    デバッグシンボルが配置されているディレクトリを指定します。<br />
    入力例：/symbols:TestResult\Out
  </td>
</tr>
<tr>
  <td>/exedir:[ ディレクトリ ]</td>
  <td>
    カバレッジ取得対象の実行ファイルが配置されているディレクトリを指定します。<br />
    入力例：/exedir:TestResult\Out
  </td>
</tr>
<tr>
  <td>/xsl:[ ファイルパス ]</td>
  <td>
    XML出力時に変換を行いたい場合、XSL形式のファイルを指定します。<br />
    入力例：/xsl:MSTestCoverageToEmma.xsl
  </td>
</tr>
</table>



実行例
-------
入力ファイル：data.coverage  
出力ファイル：data.xml の場合  

<code>CoverageConverter.exe /in:data.coverage /out:data.xml</code>



Emma形式に変換
------- 
下記からMSTestCoverageToEmma.xslをダウンロードをして、  
実行時に「/xsl:」に指定して下さい。  
http://wiki.hudson-ci.org/pages/viewpageattachments.action?pageId=41878013&metadataLink=true  

<code>CoverageConverter.exe /in:data.coverage /out:data.xml /xsl:MSTestCoverageToEmma.xsl</code>
