# main




// 创建画布
$img=imagecreatetruecolor(371,688);
// 创建颜色
$red = imagecolorallocate($img, 255, 0, 0);
$blue = imagecolorallocate($img, 0, 0, 255);
$green = imagecolorallocate($img, 0, 255, 0);
$gray = imagecolorallocate($img, 200, 200, 200);
$while = imagecolorallocate($img, 255, 255, 255);

//填充颜色
imagefill($img, 100, 0, $while);
//创建一个点
//imagesetpixel($img, 20, 20, $red);
// 随机创建1000个点
//for ($i = 0; $i < 1000; $i++) {
//    imagesetpixel($img, rand(0, 1000), rand(0, 1000), $red);
//}
// 绘制字符串
imagestring($img, 15, 20, 20, "MOTHER FUCK?", $gray);//水平
//输出线段
imageline($img, 21, 50, 130, 50, $gray);
imageline($img, 130, 50, 150, 70, $gray);
$src_img = 'http://img2.lepucdn.cn/lepu-upload/2019-01/eb/fc/ebfcd54b7406283fb85d13c4606e24a5.jpg@!750w_550h.jpg';
$src_im = imagecreatefromjpeg($src_img);
$src_info = getimagesize($src_img);
imagecopymerge($img, $src_im, 21, 70, 0, 0, 330, 250,100);
//输出矩形
//imagerectangle($img, 200, 200, 400, 400, $blue);//不填充
//imagefilledrectangle($img, 200, 400, 400, 600, $blue);//填充
//绘制多边形   imagefilledpolygon----填充
//imagepolygon($img, array(0, 0, 100, 200, 300, 200), 3, $blue);
//绘制椭圆（正圆）
//imageellipse($img, 600, 600, 200, 200, $blue);
//imagefilledellipse($img, 800, 600, 200, 200, $blue);

//imagestringup($img, 15, 600, 200, "string", $blue);//垂直
// 绘制字符
//imagechar($img, 5, 800, 200, 'H', $blue);
//imagecharup($img, 5, 800, 200, 'H', $blue);
//绘制文本
//imagettftext($img, 20, 0, 500, 500, $blue, '', '旺铺出租，先到先得');
//imagestring($img, 15, 600, 200, "", $blue);//水平
/*当上面的字体出现乱码时，使用下面的函数转换编码
string iconv ( string in_charset, string out_charset, string str )*/
//imagecopyresampled($img, "dd.jpg", 200, 200, 200, 200, 200, 200, 200, 200);
//输出图像
header('content-type:image/png');
imagepng($img);
//销毁图像
//imagedestroy($img);
