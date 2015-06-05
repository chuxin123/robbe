#Robbe函数集合.

# Robbe函数集合 #

**1.rb\_ucode\_utf8(ucode);**

作用：将给定的unicode编码转换为utf-8字符。

返回：转换后的UTF-8字符串。

**2.rb\_utf8\_ucode(str);**

作用：获取给定的UTF-8字符的unicode编码。

返回：对应utf-8字符的unicode编码。

**3.rb\_utf8\_bytes(str);**

作用：返回给定的utf-8字符占用的字节数。

返回：对应utf-8字符的字节数。

**4.rb\_dic\_exist(type, str);**

作用：查看给定的字符串是否为一个词条（词库查找）。

返回：TRUE表示是词库中的一个词条, FALSE不是。

**5.rb\_dic\_get(type, str);**

作用：返回对应utf-8字符的信息。（长度，统计词频）。

返回：数组。


**6.rb\_split(str, mode);**

作用：使用对应的模式对给定的字符串进行friso分词。

返回：数组。

请看下面的使用案例：

```
echo "constant access:<br />";
echo "complex mode: ".__RB_COMPLEX_MODE__.", simple mode: ".__RB_SIMPLE_MODE__."<br />";
echo "rb_ucode_utf8(20013)=".rb_ucode_utf8(20013)."<br />";
echo "rb_utf8_ucode(中)=".rb_utf8_ucode("中")."<br />";
echo "rb_utf8_bytes(中)=".rb_utf8_bytes("中")."<br /><br />";

echo "词库函数：<br />";
echo "rb_dic_exist(研究) ? ".rb_dic_exist(__RB_LEX_CJK_WORDS__, "研究")."<br />";

$_entry = rb_dic_get(__RB_LEX_CJK_WORDS__, "你");
echo "rb_dic_get(你)：<br />";
echo "|——length: ".$_entry["length"].", freq: ".$_entry["freq"]."<br /><br />";

echo "分词函数：<br />";
$__str__ = "robbe高性能php中文分词组件。";
echo "rb_split(\"" . $__str__ . "\")：<br />";
$_result = rb_split($__str__, __RB_COMPLEX_MODE__);
foreach ( $_result as $_value ) {
	echo $_value."/ ";
}
```

系统常量说明：
```
1.__RB_SIMPLE_MODE__

用于：rb_split()中，指定为简易分词模式。

2.__RB_COMPLEX_MODE__

用于：rb_split()中，指定为复杂分词模式。

3.以下常量用于：rb_dic_exist()和rb_dic_get()函数中，对应friso词库的九个类别：

__RB_LEX_CJK_WORDS__

__RB_LEX_CJK_UNITS__

__RB_LEX_MIX_WORDS__

__RB_LEX_CN_LNAME__

__RB_LEX_CN_SNAME__

__RB_LEX_CN_DNAME1__

__RB_LEX_CN_DNAME2__

__RB_LEX_CN_LNA__

__RB_LEX_STOPWORDS__

表示操作的词库类别。
```