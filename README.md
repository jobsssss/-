# code-fragment
日常工作中代码积累

**PHP 提供下载文件**
```
<?php
$file = 'monkey.gif';

if (file_exists($file)) {
    header('Content-Description: File Transfer');
    header('Content-Type: application/octet-stream');
    header('Content-Disposition: attachment; filename="'.basename($file).'"');
    header('Expires: 0');
    header('Cache-Control: must-revalidate');
    header('Pragma: public');
    header('Content-Length: ' . filesize($file));
    readfile($file);
    exit;
}
?> 
```
**header content-type参数列表**
```
Content-type 的说明：
'hqx' -> 'application/mac-binhex40',
'cpt' -> 'application/mac-compactpro',
'doc' -> 'application/msword',
'bin' -> 'application/octet-stream',
'dms' -> 'application/octet-stream',
'lha' -> 'application/octet-stream',
'lzh' -> 'application/octet-stream',
'exe' -> 'application/octet-stream',
'class' -> 'application/octet-stream',
'so' -> 'application/octet-stream',
'dll' -> 'application/octet-stream',
'oda' -> 'application/oda',
'pdf' -> 'application/pdf',
'ai' -> 'application/postscript',
'eps' -> 'application/postscript',
'ps' -> 'application/postscript',
'smi' -> 'application/smil',
'smil' -> 'application/smil',
'mif' -> 'application/vnd.mif',
'xls' -> 'application/vnd.ms-excel',
'ppt' -> 'application/vnd.ms-powerpoint',
'wbxml' -> 'application/vnd.wap.wbxml',
'wmlc' -> 'application/vnd.wap.wmlc',
'wmlsc' -> 'application/vnd.wap.wmlscriptc',
'bcpio' -> 'application/x-bcpio',
'vcd' -> 'application/x-cdlink',
'pgn' -> 'application/x-chess-pgn',
'cpio' -> 'application/x-cpio',
'csh' -> 'application/x-csh',
'dcr' -> 'application/x-director',
'dir' -> 'application/x-director',
'dxr' -> 'application/x-director',
'dvi' -> 'application/x-dvi',
'spl' -> 'application/x-futuresplash',
'gtar' -> 'application/x-gtar',
'hdf' -> 'application/x-hdf',
'js' -> 'application/x-javas
cript',
'skp' -> 'application/x-koan',
'skd' -> 'application/x-koan',
'skt' -> 'application/x-koan',
'skm' -> 'application/x-koan',
'latex' -> 'application/x-latex',
'nc' -> 'application/x-netcdf',
'cdf' -> 'application/x-netcdf',
'sh' -> 'application/x-sh',
'shar' -> 'application/x-shar',
'swf' -> 'application/x-shockwave-flash',
'sit' -> 'application/x-stuffit',
'sv4cpio' -> 'application/x-sv4cpio',
'sv4crc' -> 'application/x-sv4crc',
'tar' -> 'application/x-tar',
'tcl' -> 'application/x-tcl',
'tex' -> 'application/x-tex',
'texinfo' -> 'application/x-texinfo',
'texi' -> 'application/x-texinfo',
't' -> 'application/x-troff',
'tr' -> 'application/x-troff',
'roff' -> 'application/x-troff',
'man' -> 'application/x-troff-man',
'me' -> 'application/x-troff-me',
'ms' -> 'application/x-troff-ms',
'ustar' -> 'application/x-ustar',
'src' -> 'application/x-wais-source',
'xhtml' 'application/xhtml+xml',
'xht' -> 'application/xhtml+xml',
'zip' -> 'application/zip',
'au' -> 'audio/basic',
'snd' -> 'audio/basic',
'mid' -> 'audio/midi',
'midi' -> 'audio/midi',
'kar' -> 'audio/midi',
'mpga' -> 'audio/mpeg',
'mp2' -> 'audio/mpeg',
'mp3' -> 'audio/mpeg',
'aif' -> 'audio/x-aiff',
'aiff' -> 'audio/x-aiff',
'aifc' -> 'audio/x-aiff',
'm3u' -> 'audio/x-mpegurl',
'ram' -> 'audio/x-pn-realaudio',
'rm' -> 'audio/x-pn-realaudio',
'rpm' -> 'audio/x-pn-realaudio-plugin',
'ra' -> 'audio/x-realaudio',
'wav' -> 'audio/x-wav',
'pdb' -> 'chemical/x-pdb',
'xyz' -> 'chemical/x-xyz',
'bmp' -> 'image/bmp',
'gif' -> 'image/gif',
'ief' -> 'image/ief',
'jpeg' -> 'image/jpeg',
'jpg' -> 'image/jpeg',
'jpe' -> 'image/jpeg',
'png' -> 'image/png',
'tiff' -> 'image/tiff',
'tif' -> 'image/tiff',
'djvu' -> 'image/vnd.djvu',
'djv' -> 'image/vnd.djvu',
'wbmp' -> 'image/vnd.wap.wbmp',
'ras' -> 'image/x-cmu-raster',
'pnm' -> 'image/x-portable-anymap',
'pbm' -> 'image/x-portable-bitmap',
'pgm' -> 'image/x-portable-graymap',
'ppm' -> 'image/x-portable-pixmap',
'rgb' -> 'image/x-rgb',
'xbm' -> 'image/x-xbitmap',
'xpm' -> 'image/x-xpixmap',
'xwd' -> 'image/x-xwindowdump',
'igs' -> 'model/iges',
'iges' -> 'model/iges',
'msh' -> 'model/mesh',
'mesh' -> 'model/mesh',
'silo' -> 'model/mesh',
'wrl' -> 'model/vrml',
'vrml' -> 'model/vrml',
'css' -> 'text/css',
'html' -> 'text/html',
'htm' -> 'text/html',
'asc' -> 'text/plain',
'txt' -> 'text/plain',
'rtx' -> 'text/richtext',
'rtf' -> 'text/rtf',
'sgml' -> 'text/sgml',
'sgm' -> 'text/sgml',
'tsv' -> 'text/tab-separated-values',
'wml' -> 'text/vnd.wap.wml',
'wmls' -> 'text/vnd.wap.wmlscript',
'etx' -> 'text/x-setext',
'xsl' -> 'text/xml',
'xml' -> 'text/xml',
'mpeg' -> 'video/mpeg',
'mpg' -> 'video/mpeg',
'mpe' -> 'video/mpeg',
'qt' -> 'video/quicktime',
'mov' -> 'video/quicktime',
'mxu' -> 'video/vnd.mpegurl',
'avi' -> 'video/x-msvideo',
'movie' -> 'video/x-sgi-movie',
'ice' -> 'x-conference/x-cooltalk'
```

**header 参数汇总**
```
<?php
header('HTTP/1.1 200 OK'); // ok 正常访问
header('HTTP/1.1 404 Not Found'); //通知浏览器 页面不存在
header('HTTP/1.1 301 Moved Permanently'); //设置地址被永久的重定向 301
header('Location: http://www.ithhc.cn/'); //跳转到一个新的地址
header('Refresh: 10; url=http://www.ithhc.cn/'); //延迟转向 也就是隔几秒跳转
header('X-Powered-By: PHP/6.0.0'); //修改 X-Powered-By信息
header('Content-language: en'); //文档语言
header('Content-Length: 1234'); //设置内容长度
header('Last-Modified: '.gmdate('D, d M Y H:i:s', $time).' GMT'); //告诉浏览器最后一次修改时间
header('HTTP/1.1 304 Not Modified'); //告诉浏览器文档内容没有发生改变

###内容类型###
header('Content-Type: text/html; charset=utf-8'); //网页编码
header('Content-Type: text/plain'); //纯文本格式
header('Content-Type: image/jpeg'); //JPG、JPEG 
header('Content-Type: application/zip'); // ZIP文件
header('Content-Type: application/pdf'); // PDF文件
header('Content-Type: audio/mpeg'); // 音频文件 
header('Content-type: text/css'); //css文件
header('Content-type: text/javascript'); //js文件
header('Content-type: application/json'); //json
header('Content-type: application/pdf'); //pdf
header('Content-type: text/xml'); //xml
header('Content-Type: application/x-shockw**e-flash'); //Flash动画

######

###声明一个下载的文件###
header('Content-Type: application/octet-stream');
header('Content-Disposition: attachment; filename="ITblog.zip"');
header('Content-Transfer-Encoding: binary');
readfile('test.zip');
######

###对当前文档禁用缓存###
header('Cache-Control: no-cache, no-store, max-age=0, must-revalidate');
header('Expires: Mon, 26 Jul 1997 05:00:00 GMT');
######

###显示一个需要验证的登陆对话框### 
header('HTTP/1.1 401 Unauthorized'); 
header('WWW-Authenticate: Basic realm="Top Secret"'); 
######

###声明一个需要下载的xls文件###
header('Content-Disposition: attachment; filename=ithhc.xlsx');
header('Content-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet');
header('Content-Length: '.filesize('./test.xls')); 
header('Content-Transfer-Encoding: binary'); 
header('Cache-Control: must-revalidate'); 
header('Pragma: public'); 
readfile('./test.xls'); 
######
?>
```

**PHP 通过出生日期算年龄**
```
/**
 * 通过出生日期获取具体年龄
 * @param type date
 * @return type number
 */
function get_age($birthday)
{
    $age = date('Y', time()) - date('Y', strtotime($birthday)) - 1;  
    if (date('m', time()) == date('m', strtotime($birthday))){  
        if (date('d', time()) > date('d', strtotime($birthday))){  
        $age++;  
        }  
    }elseif (date('m', time()) > date('m', strtotime($birthday))){  
        $age++;  
    }  
    return $age;  
}
```

**把文件尺寸数字转换为易读的单位**
```
/**
 * 将文件尺寸转换成易读的单位，比如:get_nature_size_unit(1203, 0) 输出1.17Kb
 * @param $size
 * @param $unit_index 0表示BYTE，1：KB；2：MB；3：GB；4：TB
 * @return size
 */
function get_nature_size_unit($size, $unit_index){
    $units = ['BYTE', 'KB', 'MB', 'GB' ,'TB'];
    if ($size < 1024) {
        return round($size,2).$units[$unit_index];
    }
    if ($size >= 1024) {
        return get_nature_size_unit($size/1024, ++$unit_index);
    }
}
```
*调用效果*
```
echo get_nature_size_unit(1013737824,0);
输出:966.78MB
```

**Laravel 批量更新(update)数据表，无阻塞**
```
/**
 * 批量更新表的值，防止阻塞
 * @note 生成的SQL语句如下：
 * update mj_node set sort = case id
 *      when 13 then 1
 *      when 1 then 4
 *      when 7 then 5
 *      when 8 then 6
 *      when 9 then 7
 *      when 10 then 8
 *      when 11 then 9
 *      when 12 then 10
 * end where id in (13,1,7,8,9,10,11,12)
 * @param $conditions_field 条件字段
 * @param $values_field  需要被更新的字段
 * @param $conditions
 * @param $values
 * @return int
 */
public function batchUpdate($conditions_field, $values_field, $conditions, $values)
{
    $table = $this->model->getFullTableName();//返回完整表名，自己在项目中定义
    $sql   = 'update ' . $table . ' set '. $values_field .' = case ' .$conditions_field;
    foreach ($conditions as $key => $condition) {
        $sql .= ' when ' . $condition . ' then ?';
    }
    $sql .= ' end where id in (' . implode(',', $conditions) . ')';
    return DB::update($sql, $values);//项目中需要引入DB  facade
}
```

**php检查密码的强度**
```
/**
 * 设置一个密码强度等级规则，依次返回不同等级，返回的值越大，代表密码复杂度越强
 * @param $str
 * @return int
 */
function codes($str)
{
    $score = 0;
    if (preg_match("/[0-9]+/", $str)) {
        $score++;
    }
    if (preg_match("/[0-9]{3,}/", $str)) {
        $score++;
    }
    if (preg_match("/[a-z]+/", $str)) {
        $score++;
    }
    if (preg_match("/[a-z]{3,}/", $str)) {
        $score++;
    }
    if (preg_match("/[A-Z]+/", $str)) {
        $score++;
    }
    if (preg_match("/[A-Z]{3,}/", $str)) {
        $score++;
    }
    if (preg_match("/[_|\-|+|=|*|!|@|#|$|%|^|&|(|)]+/", $str)) {
        $score += 2;
    }
    if (preg_match("/[_|\-|+|=|*|!|@|#|$|%|^|&|(|)]{3,}/", $str)) {
        $score++;
    }
    if (strlen($str) >= 10) {
        $score++;
    }
    return $score;
}
```
*根据上面的代码衍生一个相关业务代码*
```
/**
 * 检查密码是否符合指定强度，必须大于6位，并且必须包含数字，字母和特殊字符
 * @param $password
 * @return array
 */
function password_stronger($password)
{
    if (strlen($password) < 6) {
        return array('error' => 1, 'message' => '密码长度不能低于6位');
    }
    if (!preg_match('/[0-9]+/', $password) || !preg_match('/[a-z]+/', $password) || !preg_match('/[_|\-|+|=|*|!|@|#|$|%|^|&|(|)]+/', $password)) {
        return array('error' => 2, 'message' => '密码必须是数字字母下划线组成');
    }
    return array('error' => 0, 'message' => '密码符合要求');
}
```

**php设置 HttpOnly**
可以开启配置增加全局配置：
`ini_set("session.cookie_httponly", 1);`
也可以在设置cookie的时候单独制定，开启第7个参数就是设置该cookie为HttpOnly：
`setcookie("key", "value", NULL, NULL, NULL, NULL, TRUE);`
其实做这个配置没卵用，第三方安全评测机构要求加上的，那就加上吧。知道有这么个设置就行。

**一些常用工具**
1. mycat，数据库分片工具
2. supervisor linux后台进程管理器[http://www.liaoxuefeng.com/article/0013738926914703df5e93589a14c19807f0e285194fe84000](http://)
3. rocketmq:一款消息队列工具

**php上传文件的FTP的一段示例，供参考**
```
$ftp_server = "60.12.231.144";
$ftp_user = "wodota_ting";
$ftp_pass = "wodotating!@#";
$conn_id = ftp_connect($ftp_server) or die("Couldn't connect to $ftp_server");
$login_result = ftp_login($conn_id, $ftp_user, $ftp_pass);
if ((!$conn_id) || (!$login_result)) {
    echo "FTP connection has failed!";
    echo "Attempted to connect to $ftp_server for user $ftp_user_name";
    exit;
} else {
    echo "Connected to $ftp_server, for user $ftp_user_name";
}
$source_file=$this->filepath.$this->newFileName;  //源地址
echo $source_file;
$destination_file="/testxiao/".$this->newFileName;  //目标地址
$upload = ftp_put($conn_id, $destination_file, $source_file, FTP_BINARY) or die("Couldn't connect to $ftp_server");
//ftp_close($conn_id);
if (!$upload) {
    echo "FTP upload has failed!";
} else {
    echo "Uploaded $source_file to $ftp_server as $destination_file";
}
ftp_close($conn_id);
```
**php获取客户端IP地址的正确姿势**
```
/**
 * 获取客户端IP地址
 * @param integer $type 返回类型 0 返回IP地址 1 返回IPV4地址数字
 * @param boolean $adv 是否进行高级模式获取（有可能被伪装） 
 * @return mixed
 */
function get_client_ip($type = 0,$adv=false) {
    $type       =  $type ? 1 : 0;
    static $ip  =   NULL;
    if ($ip !== NULL) return $ip[$type];
    if($adv){
        if (isset($_SERVER['HTTP_X_FORWARDED_FOR'])) {
            $arr    =   explode(',', $_SERVER['HTTP_X_FORWARDED_FOR']);
            $pos    =   array_search('unknown',$arr);
            if(false !== $pos) unset($arr[$pos]);
            $ip     =   trim($arr[0]);
        }elseif (isset($_SERVER['HTTP_CLIENT_IP'])) {
            $ip     =   $_SERVER['HTTP_CLIENT_IP'];
        }elseif (isset($_SERVER['REMOTE_ADDR'])) {
            $ip     =   $_SERVER['REMOTE_ADDR'];
        }
    }elseif (isset($_SERVER['REMOTE_ADDR'])) {
        $ip     =   $_SERVER['REMOTE_ADDR'];
    }
    // IP地址合法验证
    $long = sprintf("%u",ip2long($ip));
    $ip   = $long ? array($ip, $long) : array('0.0.0.0', 0);
    return $ip[$type];
}
```

**php生僻但是会用到的函数记录**
`func_get_args()  获取函数的所有参数`

**laravel时间相关操作**
laravel的时间处理使用的是扩展包carbon 详情参考 http://carbon.nesbot.com/docs/
```
简单用法示例: 
$model->created_at->format('Y-m-d'); //格式化时间
$model->created_at->yesterday();//昨天
$model->created_at->tomorrow();//明天
$model->created_at->diffForHumans();//与当前时间差
……
```

**单元测试记录**
```
安装(windows)：

下载 phpunit.phar http://www.phpunit.cn/
将phpunit.phar 放到指定目录下并配置好环境变量
进入 phpunit.phar 目录，并输入 echo @php "%~dp0phpunit.phar" %* > phpunit.cmd
接着输入 phpunit --version ，如果返回的内容为 PHPUnit x.y.z by Sebastian Bergmann and contributors. 即代表安装好
```
**语法积累**
1. 在数组的前面加上 `...`作为参数传入到函数中，可以展开数组的每一个元素，作为函数的参数传递。回调函数 `call_user_func_array()` 也可以达到相同的效果

** Http状态码**
http://tool.oschina.net/commons?type=5
```
状态码 含义
100 客户端应当继续发送请求。这个临时响应是用来通知客户端它的部分请求已经被服务器接收，且仍未被拒绝。客户端应当继续发送请求的剩余部分，或者如果请求已经完成，忽略这个响应。服务器必须在请求完成后向客户端发送一个最终响应。
101 服务器已经理解了客户端的请求，并将通过Upgrade 消息头通知客户端采用不同的协议来完成这个请求。在发送完这个响应最后的空行后，服务器将会切换到在Upgrade 消息头中定义的那些协议。 　　只有在切换新的协议更有好处的时候才应该采取类似措施。例如，切换到新的HTTP 版本比旧版本更有优势，或者切换到一个实时且同步的协议以传送利用此类特性的资源。
102 由WebDAV（RFC 2518）扩展的状态码，代表处理将被继续执行。
200 请求已成功，请求所希望的响应头或数据体将随此响应返回。
201 请求已经被实现，而且有一个新的资源已经依据请求的需要而建立，且其 URI 已经随Location 头信息返回。假如需要的资源无法及时建立的话，应当返回 '202 Accepted'。
202 服务器已接受请求，但尚未处理。正如它可能被拒绝一样，最终该请求可能会也可能不会被执行。在异步操作的场合下，没有比发送这个状态码更方便的做法了。 　　返回202状态码的响应的目的是允许服务器接受其他过程的请求（例如某个每天只执行一次的基于批处理的操作），而不必让客户端一直保持与服务器的连接直到批处理操作全部完成。在接受请求处理并返回202状态码的响应应当在返回的实体中包含一些指示处理当前状态的信息，以及指向处理状态监视器或状态预测的指针，以便用户能够估计操作是否已经完成。
203 服务器已成功处理了请求，但返回的实体头部元信息不是在原始服务器上有效的确定集合，而是来自本地或者第三方的拷贝。当前的信息可能是原始版本的子集或者超集。例如，包含资源的元数据可能导致原始服务器知道元信息的超级。使用此状态码不是必须的，而且只有在响应不使用此状态码便会返回200 OK的情况下才是合适的。
204 服务器成功处理了请求，但不需要返回任何实体内容，并且希望返回更新了的元信息。响应可能通过实体头部的形式，返回新的或更新后的元信息。如果存在这些头部信息，则应当与所请求的变量相呼应。 　　如果客户端是浏览器的话，那么用户浏览器应保留发送了该请求的页面，而不产生任何文档视图上的变化，即使按照规范新的或更新后的元信息应当被应用到用户浏览器活动视图中的文档。 　　由于204响应被禁止包含任何消息体，因此它始终以消息头后的第一个空行结尾。
205 服务器成功处理了请求，且没有返回任何内容。但是与204响应不同，返回此状态码的响应要求请求者重置文档视图。该响应主要是被用于接受用户输入后，立即重置表单，以便用户能够轻松地开始另一次输入。 　　与204响应一样，该响应也被禁止包含任何消息体，且以消息头后的第一个空行结束。
206 服务器已经成功处理了部分 GET 请求。类似于 FlashGet 或者迅雷这类的 HTTP 下载工具都是使用此类响应实现断点续传或者将一个大文档分解为多个下载段同时下载。 　　该请求必须包含 Range 头信息来指示客户端希望得到的内容范围，并且可能包含 If-Range 来作为请求条件。 　　响应必须包含如下的头部域： 　　Content-Range 用以指示本次响应中返回的内容的范围；如果是 Content-Type 为 multipart/byteranges 的多段下载，则每一 multipart 段中都应包含 Content-Range 域用以指示本段的内容范围。假如响应中包含 Content-Length，那么它的数值必须匹配它返回的内容范围的真实字节数。 　　Date 　　ETag 和/或 Content-Location，假如同样的请求本应该返回200响应。 　　Expires, Cache-Control，和/或 Vary，假如其值可能与之前相同变量的其他响应对应的值不同的话。 　　假如本响应请求使用了 If-Range 强缓存验证，那么本次响应不应该包含其他实体头；假如本响应的请求使用了 If-Range 弱缓存验证，那么本次响应禁止包含其他实体头；这避免了缓存的实体内容和更新了的实体头信息之间的不一致。否则，本响应就应当包含所有本应该返回200响应中应当返回的所有实体头部域。 　　假如 ETag 或 Last-Modified 头部不能精确匹配的话，则客户端缓存应禁止将206响应返回的内容与之前任何缓存过的内容组合在一起。 　　任何不支持 Range 以及 Content-Range 头的缓存都禁止缓存206响应返回的内容。
207 由WebDAV(RFC 2518)扩展的状态码，代表之后的消息体将是一个XML消息，并且可能依照之前子请求数量的不同，包含一系列独立的响应代码。
300 被请求的资源有一系列可供选择的回馈信息，每个都有自己特定的地址和浏览器驱动的商议信息。用户或浏览器能够自行选择一个首选的地址进行重定向。 　　除非这是一个 HEAD 请求，否则该响应应当包括一个资源特性及地址的列表的实体，以便用户或浏览器从中选择最合适的重定向地址。这个实体的格式由 Content-Type 定义的格式所决定。浏览器可能根据响应的格式以及浏览器自身能力，自动作出最合适的选择。当然，RFC 2616规范并没有规定这样的自动选择该如何进行。 　　如果服务器本身已经有了首选的回馈选择，那么在 Location 中应当指明这个回馈的 URI；浏览器可能会将这个 Location 值作为自动重定向的地址。此外，除非额外指定，否则这个响应也是可缓存的。
301 被请求的资源已永久移动到新位置，并且将来任何对此资源的引用都应该使用本响应返回的若干个 URI 之一。如果可能，拥有链接编辑功能的客户端应当自动把请求的地址修改为从服务器反馈回来的地址。除非额外指定，否则这个响应也是可缓存的。 　　新的永久性的 URI 应当在响应的 Location 域中返回。除非这是一个 HEAD 请求，否则响应的实体中应当包含指向新的 URI 的超链接及简短说明。 　　如果这不是一个 GET 或者 HEAD 请求，因此浏览器禁止自动进行重定向，除非得到用户的确认，因为请求的条件可能因此发生变化。 　　注意：对于某些使用 HTTP/1.0 协议的浏览器，当它们发送的 POST 请求得到了一个301响应的话，接下来的重定向请求将会变成 GET 方式。
302 请求的资源现在临时从不同的 URI 响应请求。由于这样的重定向是临时的，客户端应当继续向原有地址发送以后的请求。只有在Cache-Control或Expires中进行了指定的情况下，这个响应才是可缓存的。 　　新的临时性的 URI 应当在响应的 Location 域中返回。除非这是一个 HEAD 请求，否则响应的实体中应当包含指向新的 URI 的超链接及简短说明。 　　如果这不是一个 GET 或者 HEAD 请求，那么浏览器禁止自动进行重定向，除非得到用户的确认，因为请求的条件可能因此发生变化。 　　注意：虽然RFC 1945和RFC 2068规范不允许客户端在重定向时改变请求的方法，但是很多现存的浏览器将302响应视作为303响应，并且使用 GET 方式访问在 Location 中规定的 URI，而无视原先请求的方法。状态码303和307被添加了进来，用以明确服务器期待客户端进行何种反应。
303 对应当前请求的响应可以在另一个 URI 上被找到，而且客户端应当采用 GET 的方式访问那个资源。这个方法的存在主要是为了允许由脚本激活的POST请求输出重定向到一个新的资源。这个新的 URI 不是原始资源的替代引用。同时，303响应禁止被缓存。当然，第二个请求（重定向）可能被缓存。 　　新的 URI 应当在响应的 Location 域中返回。除非这是一个 HEAD 请求，否则响应的实体中应当包含指向新的 URI 的超链接及简短说明。 　　注意：许多 HTTP/1.1 版以前的 浏览器不能正确理解303状态。如果需要考虑与这些浏览器之间的互动，302状态码应该可以胜任，因为大多数的浏览器处理302响应时的方式恰恰就是上述规范要求客户端处理303响应时应当做的。
304 如果客户端发送了一个带条件的 GET 请求且该请求已被允许，而文档的内容（自上次访问以来或者根据请求的条件）并没有改变，则服务器应当返回这个状态码。304响应禁止包含消息体，因此始终以消息头后的第一个空行结尾。 　　该响应必须包含以下的头信息： 　　Date，除非这个服务器没有时钟。假如没有时钟的服务器也遵守这些规则，那么代理服务器以及客户端可以自行将 Date 字段添加到接收到的响应头中去（正如RFC 2068中规定的一样），缓存机制将会正常工作。 　　ETag 和/或 Content-Location，假如同样的请求本应返回200响应。 　　Expires, Cache-Control，和/或Vary，假如其值可能与之前相同变量的其他响应对应的值不同的话。 　　假如本响应请求使用了强缓存验证，那么本次响应不应该包含其他实体头；否则（例如，某个带条件的 GET 请求使用了弱缓存验证），本次响应禁止包含其他实体头；这避免了缓存了的实体内容和更新了的实体头信息之间的不一致。 　　假如某个304响应指明了当前某个实体没有缓存，那么缓存系统必须忽视这个响应，并且重复发送不包含限制条件的请求。 　　假如接收到一个要求更新某个缓存条目的304响应，那么缓存系统必须更新整个条目以反映所有在响应中被更新的字段的值。
305 被请求的资源必须通过指定的代理才能被访问。Location 域中将给出指定的代理所在的 URI 信息，接收者需要重复发送一个单独的请求，通过这个代理才能访问相应资源。只有原始服务器才能建立305响应。 　　注意：RFC 2068中没有明确305响应是为了重定向一个单独的请求，而且只能被原始服务器建立。忽视这些限制可能导致严重的安全后果。
306 在最新版的规范中，306状态码已经不再被使用。
307 请求的资源现在临时从不同的URI 响应请求。由于这样的重定向是临时的，客户端应当继续向原有地址发送以后的请求。只有在Cache-Control或Expires中进行了指定的情况下，这个响应才是可缓存的。 　　新的临时性的URI 应当在响应的 Location 域中返回。除非这是一个HEAD 请求，否则响应的实体中应当包含指向新的URI 的超链接及简短说明。因为部分浏览器不能识别307响应，因此需要添加上述必要信息以便用户能够理解并向新的 URI 发出访问请求。 　　如果这不是一个GET 或者 HEAD 请求，那么浏览器禁止自动进行重定向，除非得到用户的确认，因为请求的条件可能因此发生变化。
400 1、语义有误，当前请求无法被服务器理解。除非进行修改，否则客户端不应该重复提交这个请求。 　　2、请求参数有误。
401 当前请求需要用户验证。该响应必须包含一个适用于被请求资源的 WWW-Authenticate 信息头用以询问用户信息。客户端可以重复提交一个包含恰当的 Authorization 头信息的请求。如果当前请求已经包含了 Authorization 证书，那么401响应代表着服务器验证已经拒绝了那些证书。如果401响应包含了与前一个响应相同的身份验证询问，且浏览器已经至少尝试了一次验证，那么浏览器应当向用户展示响应中包含的实体信息，因为这个实体信息中可能包含了相关诊断信息。参见RFC 2617。
402 该状态码是为了将来可能的需求而预留的。
403 服务器已经理解请求，但是拒绝执行它。与401响应不同的是，身份验证并不能提供任何帮助，而且这个请求也不应该被重复提交。如果这不是一个 HEAD 请求，而且服务器希望能够讲清楚为何请求不能被执行，那么就应该在实体内描述拒绝的原因。当然服务器也可以返回一个404响应，假如它不希望让客户端获得任何信息。
404 请求失败，请求所希望得到的资源未被在服务器上发现。没有信息能够告诉用户这个状况到底是暂时的还是永久的。假如服务器知道情况的话，应当使用410状态码来告知旧资源因为某些内部的配置机制问题，已经永久的不可用，而且没有任何可以跳转的地址。404这个状态码被广泛应用于当服务器不想揭示到底为何请求被拒绝或者没有其他适合的响应可用的情况下。
405 请求行中指定的请求方法不能被用于请求相应的资源。该响应必须返回一个Allow 头信息用以表示出当前资源能够接受的请求方法的列表。 　　鉴于 PUT，DELETE 方法会对服务器上的资源进行写操作，因而绝大部分的网页服务器都不支持或者在默认配置下不允许上述请求方法，对于此类请求均会返回405错误。
406 请求的资源的内容特性无法满足请求头中的条件，因而无法生成响应实体。 　　除非这是一个 HEAD 请求，否则该响应就应当返回一个包含可以让用户或者浏览器从中选择最合适的实体特性以及地址列表的实体。实体的格式由 Content-Type 头中定义的媒体类型决定。浏览器可以根据格式及自身能力自行作出最佳选择。但是，规范中并没有定义任何作出此类自动选择的标准。
407 　与401响应类似，只不过客户端必须在代理服务器上进行身份验证。代理服务器必须返回一个 Proxy-Authenticate 用以进行身份询问。客户端可以返回一个 Proxy-Authorization 信息头用以验证。参见RFC 2617。
408 请求超时。客户端没有在服务器预备等待的时间内完成一个请求的发送。客户端可以随时再次提交这一请求而无需进行任何更改。
409 由于和被请求的资源的当前状态之间存在冲突，请求无法完成。这个代码只允许用在这样的情况下才能被使用：用户被认为能够解决冲突，并且会重新提交新的请求。该响应应当包含足够的信息以便用户发现冲突的源头。 　　冲突通常发生于对 PUT 请求的处理中。例如，在采用版本检查的环境下，某次 PUT 提交的对特定资源的修改请求所附带的版本信息与之前的某个（第三方）请求向冲突，那么此时服务器就应该返回一个409错误，告知用户请求无法完成。此时，响应实体中很可能会包含两个冲突版本之间的差异比较，以便用户重新提交归并以后的新版本。
410 被请求的资源在服务器上已经不再可用，而且没有任何已知的转发地址。这样的状况应当被认为是永久性的。如果可能，拥有链接编辑功能的客户端应当在获得用户许可后删除所有指向这个地址的引用。如果服务器不知道或者无法确定这个状况是否是永久的，那么就应该使用404状态码。除非额外说明，否则这个响应是可缓存的。 　　410响应的目的主要是帮助网站管理员维护网站，通知用户该资源已经不再可用，并且服务器拥有者希望所有指向这个资源的远端连接也被删除。这类事件在限时、增值服务中很普遍。同样，410响应也被用于通知客户端在当前服务器站点上，原本属于某个个人的资源已经不再可用。当然，是否需要把所有永久不可用的资源标记为'410 Gone'，以及是否需要保持此标记多长时间，完全取决于服务器拥有者。
411 服务器拒绝在没有定义 Content-Length 头的情况下接受请求。在添加了表明请求消息体长度的有效 Content-Length 头之后，客户端可以再次提交该请求。
412 服务器在验证在请求的头字段中给出先决条件时，没能满足其中的一个或多个。这个状态码允许客户端在获取资源时在请求的元信息（请求头字段数据）中设置先决条件，以此避免该请求方法被应用到其希望的内容以外的资源上。
413 服务器拒绝处理当前请求，因为该请求提交的实体数据大小超过了服务器愿意或者能够处理的范围。此种情况下，服务器可以关闭连接以免客户端继续发送此请求。 　　如果这个状况是临时的，服务器应当返回一个 Retry-After 的响应头，以告知客户端可以在多少时间以后重新尝试。
414 请求的URI 长度超过了服务器能够解释的长度，因此服务器拒绝对该请求提供服务。这比较少见，通常的情况包括： 　　本应使用POST方法的表单提交变成了GET方法，导致查询字符串（Query String）过长。 　　重定向URI “黑洞”，例如每次重定向把旧的 URI 作为新的 URI 的一部分，导致在若干次重定向后 URI 超长。 　　客户端正在尝试利用某些服务器中存在的安全漏洞攻击服务器。这类服务器使用固定长度的缓冲读取或操作请求的 URI，当 GET 后的参数超过某个数值后，可能会产生缓冲区溢出，导致任意代码被执行[1]。没有此类漏洞的服务器，应当返回414状态码。
415 对于当前请求的方法和所请求的资源，请求中提交的实体并不是服务器中所支持的格式，因此请求被拒绝。
416 如果请求中包含了 Range 请求头，并且 Range 中指定的任何数据范围都与当前资源的可用范围不重合，同时请求中又没有定义 If-Range 请求头，那么服务器就应当返回416状态码。 　　假如 Range 使用的是字节范围，那么这种情况就是指请求指定的所有数据范围的首字节位置都超过了当前资源的长度。服务器也应当在返回416状态码的同时，包含一个 Content-Range 实体头，用以指明当前资源的长度。这个响应也被禁止使用 multipart/byteranges 作为其 Content-Type。
417 在请求头 Expect 中指定的预期内容无法被服务器满足，或者这个服务器是一个代理服务器，它有明显的证据证明在当前路由的下一个节点上，Expect 的内容无法被满足。
421 从当前客户端所在的IP地址到服务器的连接数超过了服务器许可的最大范围。通常，这里的IP地址指的是从服务器上看到的客户端地址（比如用户的网关或者代理服务器地址）。在这种情况下，连接数的计算可能涉及到不止一个终端用户。
422 从当前客户端所在的IP地址到服务器的连接数超过了服务器许可的最大范围。通常，这里的IP地址指的是从服务器上看到的客户端地址（比如用户的网关或者代理服务器地址）。在这种情况下，连接数的计算可能涉及到不止一个终端用户。
422 请求格式正确，但是由于含有语义错误，无法响应。（RFC 4918 WebDAV）423 Locked 　　当前资源被锁定。（RFC 4918 WebDAV）
424 由于之前的某个请求发生的错误，导致当前请求失败，例如 PROPPATCH。（RFC 4918 WebDAV）
425 在WebDav Advanced Collections 草案中定义，但是未出现在《WebDAV 顺序集协议》（RFC 3658）中。
426 客户端应当切换到TLS/1.0。（RFC 2817）
449 由微软扩展，代表请求应当在执行完适当的操作后进行重试。
500 服务器遇到了一个未曾预料的状况，导致了它无法完成对请求的处理。一般来说，这个问题都会在服务器的程序码出错时出现。
501 服务器不支持当前请求所需要的某个功能。当服务器无法识别请求的方法，并且无法支持其对任何资源的请求。
502 作为网关或者代理工作的服务器尝试执行请求时，从上游服务器接收到无效的响应。
503 由于临时的服务器维护或者过载，服务器当前无法处理请求。这个状况是临时的，并且将在一段时间以后恢复。如果能够预计延迟时间，那么响应中可以包含一个 Retry-After 头用以标明这个延迟时间。如果没有给出这个 Retry-After 信息，那么客户端应当以处理500响应的方式处理它。 　　注意：503状态码的存在并不意味着服务器在过载的时候必须使用它。某些服务器只不过是希望拒绝客户端的连接。
504 作为网关或者代理工作的服务器尝试执行请求时，未能及时从上游服务器（URI标识出的服务器，例如HTTP、FTP、LDAP）或者辅助服务器（例如DNS）收到响应。 　　注意：某些代理服务器在DNS查询超时时会返回400或者500错误
505 服务器不支持，或者拒绝支持在请求中使用的 HTTP 版本。这暗示着服务器不能或不愿使用与客户端相同的版本。响应中应当包含一个描述了为何版本不被支持以及服务器支持哪些协议的实体。
506 由《透明内容协商协议》（RFC 2295）扩展，代表服务器存在内部配置错误：被请求的协商变元资源被配置为在透明内容协商中使用自己，因此在一个协商处理中不是一个合适的重点。
507 服务器无法存储完成请求所必须的内容。这个状况被认为是临时的。WebDAV (RFC 4918)
509 服务器达到带宽限制。这不是一个官方的状态码，但是仍被广泛使用。
510 获取资源所需要的策略并没有没满足。（RFC 2774）

**windows下查找被占用的端口并结束占用进程**
使用命令:`netstat -ano|findstr "80"`
![](![file](https://omu8v0x3b.qnssl.com/uploads/images/201709/26/14/ksGZpkeAxa.png)
使用命令: `tasklist|findstr "1828"`, 1828根据上一步找到的对应的pid,发现是一个java.exe程序占用了80端口，如图：
![](![file](https://omu8v0x3b.qnssl.com/uploads/images/201709/26/14/Xx2MsoI4mO.png)

最后使用：`taskkill /f /t /im java.exe` 结束java.exe。
结束成功会提示：
成功： 已终止 。。。
![](![file](https://omu8v0x3b.qnssl.com/uploads/images/201709/26/14/91T6FwqN9l.png)
```

**php输出报错信息**
```
set_error_handler("custom_error");

function custom_error($errno, $errstr){
    echo "<b>Error:</b> [$errno] $errstr";
}
```
**composer dump-autoload后报错：PHP Fatal error: Uncaught TypeError: Argument 1 passed to Composer\Autoload......**
解决方案：移除homestead.ymal中的 nfs 配置

**git查看已提交的文件**
`git log --oneline --name-only -1`

**html转word**
word类：
```
class Word
{
    function start()
    {
        ob_start();
        echo '<html xmlns:o="urn:schemas-microsoft-com:office:office"
                xmlns:w="urn:schemas-microsoft-com:office:word"
                xmlns="http://www.w3.org/TR/REC-html40">';
    }

    function save($path)
    {
        echo "</html>";
        $data = ob_get_contents();
        ob_end_clean();
        $rs = $this->wirtefile($path, $data);
        if ($rs) {
            return $path;
        }
        return false;
    }

    function wirtefile($fn, $data)
    {
        chmod($fn,0777);
        $fp = fopen($fn, "w+");
        $rs = fwrite($fp, $data);
        fclose($fp);
        return $rs;
    }
}
```
一段使用示例，将html转换成word，并返回word的路径
```
/**
 * 通过给定的html内容，把内容写到word文档中去
 * @param $name  word名称
 * @param $html_content  html内容
 * @return bool
 */
function make_word($name, $html_content)
{
    $word = new Word();
    $word->start();
    $directory = getcwd() . DIRECTORY_SEPARATOR . 'attach';
    if (!is_dir($directory)) {
        mkdir($directory, 0777);
    }
    $word_name = getcwd() . DIRECTORY_SEPARATOR . 'attach' . DIRECTORY_SEPARATOR . $name;
    echo $html_content;
    $rs = $word->save($word_name);
    ob_flush();//每次执行前刷新缓存
    flush();
    return $rs;
}
```

**版本约束中破折号和波浪号的意义**
`~`和`^`的意思很接近，在x.y的情况下是一样的都是代表x.y <= 版本号 < (x+1).0，但是在版本号是x.y.z的情况下有区别，举个例子
```
~1.2.3 代表 1.2.3 <= 版本号 < 1.3.0

^1.2.3 代表 1.2.3 <= 版本号 < 2.0.0
```

**__callStatic**
定义`__callStatic`后，被静态访问的方法权限要是不可外部访问的才会执行


** linux设置时区**
``timedatectl set-timezone "Asia/Shanghai"``
