# PHP|Gmagick getQuantumDepth()函数

> Original: [https://www.geeksforgeeks.org/php-gmagick-getquantumdepth-function/](https://www.geeksforgeeks.org/php-gmagick-getquantumdepth-function/)

Gmagick：：getquantumDeep()函数是 PHP 中的一个内置函数，用于返回 Gmagick 对象的量子深度。

**语法：**

```
*public* Gmagick::getquantumdepth( void ) : array
```

**参数：**此函数不接受任何参数。

**返回值：**此函数以字符串形式返回 Gmagick 量子深度。

下面的程序演示了 PHP 中的 Gmagick：：getQuantumDeep()函数：

**程序 1：**
**原始图像：**
![https://media.geeksforgeeks.org/wp-content/uploads/geeks-21.png](img/a377156ca25e3fe93469e179d416418f.png)

```
<?php

// Create new Gmagick object
$im = new Gmagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-15.png');

// Using getquantumdepth function
print_r($im->getquantumdepth());

?>
```

发帖主题：Re：Колибри0.7.0

```
Array ( [quantumDepthLong] => 16 
        [quantumDepthString] => Q16 
) 

```

**程序 2：**
**原始图像：**
![https://media.geeksforgeeks.org/wp-content/uploads/Screenshot-from-2018-10-16-23-23-54.png](img/583fb2a26e2d28d4d8bbc47a02020896.png)

```
<?php 

$string = "Computer Science portal for Geeks!"; 

// Creating new image of above String 
// and add color
$im = new Gmagick(); 
$draw = new GmagickDraw(); 

// Fill the color in image 
$draw->setFillColor(new GmagickPixel('green')); 

// Set the text font size 
$draw->setFontSize(50); 

$metrix = $im->queryFontMetrics($draw, $string); 
$draw->annotation(0, 40, $string); 
$im->newImage($metrix['textWidth'], $metrix['textHeight'], 
        new GmagickPixel('white')); 

// Draw the image         
$im->drawImage($draw); 
$im->setImageFormat('jpeg'); 

// Using getquantumdepth function
print_r($im->getquantumdepth());

?>
```

发帖主题：Re：Колибри0.7.0

```
Array ( [quantumDepthLong] => 16 
        [quantumDepthString] => Q16 
) 

```

**引用：**[http://php.net/manual/en/gmagick.getquantumdepth.php](http://php.net/manual/en/gmagick.getquantumdepth.php)