# 打印数组中任意连续元素值 

## 例子

	int main(void)
	{
	  int array[201];
	  int i;
	
	  for (i = 0; i < 201; i++)
	    array[i] = i;
	
	  return 0;
	}

## 技巧

在gdb中，如果要打印数组中任意连续元素的值，可以使用“`p array[index]@num`”命令（`p`是`print`命令的缩写）。其中`index`是数组索引（从0开始计数），`num`是连续多少个元素。以上面代码为例：

	(gdb) p array
	$8 = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31,
	  32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62,
	  63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93,
	  94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119,
	  120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144,
	  145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169,
	  170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194,
	  195, 196, 197, 198, 199...}
	(gdb) p array[60]@10
	$9 = {60, 61, 62, 63, 64, 65, 66, 67, 68, 69}


可以看到打印了`array`数组第60~69个元素的值。  
如果要打印从数组开头连续元素的值，也可使用这个命令：“`p *array@num`”：

	(gdb) p *array@10
	$2 = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}



## 贡献者

nanxiao


