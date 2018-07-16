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
