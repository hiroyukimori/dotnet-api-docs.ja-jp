### <a name="product-versioning-changes-in-the-net-framework-46-and-later-versions"></a>.NET Framework 4.6 およびそれ以降のバージョンの製品のバージョン管理の変更点

|   |   |
|---|---|
|説明|製品のバージョン管理が .NET Framework 4、4.5、4.5.1、特におよび .NET Framework の以前のリリースから変更され、4.5.2.The 次に、変更の詳細。<ul><li>値、<code>Version</code>内のエントリ、<code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code>にキーが変更された<code>4.6.xxxxx</code>.NET Framework 4.6 およびそのポイント リリースと<code>4.7.xxxxx</code>.NET Framework 4.7 および 4.7.1 です。 .NET framework 4.5、4.5.1、および 4.5.2 では、という形式でした<code>4.5.xxxxx</code>です。</li><li>.NET Framework ファイルのファイルおよび製品のバージョン管理が変更されました 4.0.30319.x の以前のバージョン管理スキームから .NET Framework 4.6 およびそのポイント リリース 4.6.X.0 して 4.7.X.0 .NET Framework 4.7 および 4.7.1。 ファイルを右クリックして、ファイルのプロパティを表示するときに、これらの新しい値を表示できます。</li><li><xref:System.Reflection.AssemblyFileVersionAttribute>と<xref:System.Reflection.AssemblyInformationalVersionAttribute>属性マネージ アセンブリでは、バージョンの値を持つフォームでの .NET Framework 4.6 とそのポイント リリース、および .NET Framework 4.7 および 4.7.1 4.7.X.0 4.6.X.0 です。</li><li>.NET framework 4.6、4.6.1、4.6.2、4.7、および、4.7.1、<xref:System.Environment.Version?displayProperty=nameWithType>プロパティ修正したバージョン文字列を返します<code>4.0.30319.42000</code>です。 .NET framework 4、4.5、4.5.1、および 4.5.2 では、形式でバージョン文字列を返します<code>4.0.30319.xxxxx</code>(たとえば、&quot;いました: 4.0.30319.18010&quot;)。 アプリケーション コード Environment.Version プロパティに対する新しい依存関係を実行することお勧めしないことに注意してください。</li></ul>詳細については、次を参照してください。[する方法: どの .NET Framework のバージョンがインストールされているかを判断](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)です。|
|提案される解決策|一般に、.NET Framework のランタイムのバージョンやインストール ディレクトリを検出する際、アプリケーションは推奨される技法に従う必要があります。<ul><li>.NET Framework のランタイムのバージョンを検出するには、「[方法 : インストールされている .NET Framework バージョンを確認する](~/docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)」を参照してください。</li><li>.NET Framework のインストール パスを確認するには、<code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full</code> キーの <code>InstallPath</code> エントリの値を使用します。</li></ul> <blockquote> [!IMPORTANT] サブキー名は、<code>.NET Framework Setup</code> ではなく <code>NET Framework Setup</code> です。</blockquote> <ul><li>.NET Framework の共通言語ランタイムへのディレクトリ パスを確認するには、<xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory?displayProperty=nameWithType> メソッドを呼び出します。</li><li>CLR のバージョンを取得するには、<xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion?displayProperty=nameWithType> メソッドを呼び出します。 .NET Framework 4 とそのポイント リリース (.NET Framework 4.5、4.5.1、4.5.2、および .NET Framework 4.6、4.6.1、4.6.2、4.7、および 4.7.1)、文字列 v4.0.30319 を返します。</li></ul>|
|スコープ|マイナー|
|Version|4.6|
|型|ランタイム|
