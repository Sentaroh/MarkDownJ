## 1.説明

[markdownj](https://github.com/myabc/markdownj) からコピーして独自の機能を追加したものです。

## 2.追加
### 2.1.入力にInputStreamを追加
入力としてInputStreamを使用できるようにした。

### 2.2.List処理の改善
下記のケースでリスト処理されるようにした。

入力:

	### HEAD
	Head level3
	- List1

html出力:

	<h3>HEAD</h3>
	
	<p>Head level3</p>
	
	<ul>
	<li>List1</li>
	</ul>

### 2.3.行末に\<br\>タグを追加するオプション
行末が\<br\>または2つ以上の半角スペース以外の時に\<br\>タグを行末に追加する。

入力:

	### HEAD
	Head level3
	- List1

html出力:

    <h3>HEAD<br></h3>
    
    <p>Head level3<br></p>
    
    <ul>
    <li>List1<br></li>
    </ul>

## 3.使用方法
### 3.1.InputStream

	boolean append_br_tag=true;
	InputStream is=new FileInputStream(new File("/sdcard/input.md"));
	String new_out=new MarkdownProcessor().markdown(append_br_tag, is);

### 3.2.String

	boolean append_br_tag=true;
	String md_text="### HEAD\nHead level3\n- List1";
	String new_out=new MarkdownProcessor().markdown(append_br_tag, md_text);

