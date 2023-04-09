具体搭建方法看https://www.bilibili.com/video/BV1Dk4y1Y7ob/
视频内忘记说伪静态设置

下面是伪静态规则

location ~* (runtime|application)/{
	return 403;
}
location / {
	if (!-e $request_filename){
		rewrite  ^(.*)$  /index.php?s=$1  last;   break;
	}
}
