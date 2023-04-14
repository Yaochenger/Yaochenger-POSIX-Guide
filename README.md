# POSIX接口标准示例笔记



## 1 ctype.h

### 1.1 isalnum()

isalnum()函数用于测试字符，如果字符是**字母**或**数字**，则返回非零值（即真），否则返回零（即假）。isalnum()函数在许多场景中非常有用，特别是在字符串处理中。以下是一个示例代码:

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char str[] = "YouBot is awesome! 123";
   int i = 0;
   while(str[i]) {
      if (isalnum(str[i])) {
         printf("'%c' is an alphanumeric character\n", str[i]);
      } else {
         printf("'%c' is not an alphanumeric character\n", str[i]);
      }
      i++;
   }
   return 0;
}

```

在这个示例中，我们通过循环遍历给定的字符串，并使用isalnum()函数测试每个字符。如果字符是字母或数字，我们打印一条消息表示它是一个字母数字字符，否则我们打印一条消息表示它不是字母数字字符。这是一个常见的用例场景，可用于验证用户输入的密码是否只包含字母和数字。

### 1.2 isapha()

isalpha()函数用于测试字符，**如果字符是字母**（A-Z或a-z），则返回非零值（即真），否则返回零（即假）。以下是一个示例代码：

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char ch;
   printf("Enter any character: ");
   scanf("%c", &ch);
   if(isalpha(ch)) {
      printf("%c is an alphabet.", ch);
   } else {
      printf("%c is not an alphabet.", ch);
   }
   return 0;
}

```

在这个示例中，我们从用户读取一个字符并使用isalpha()函数测试它是否为字母字符。如果字符是字母字符，我们打印一条消息表示它是字母字符，否则我们打印一条消息表示它不是字母字符。这是一个常见的用例场景，可用于验证用户输入是否是字母字符。

isalpha()函数是C语言中对字符分类和操作功能的一个基本函数之一，通常与其他函数，例如isdigit()和isalnum()等一起使用，以执行更复杂的操作。

### 1.3 isblank()

isblank()函数是ctype.h头文件中定义的函数之一，用于测试一个字符是否为空格字符。

具体来说，isblank()函数用于测试字符，如果字符为空格字符（空格或制表符），则返回非零值（即真），否则返回零（即假）。以下是一个示例代码：

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char ch1 = ' ';
   char ch2 = 'A';
   if(isblank(ch1)) {
      printf("%c is a blank character.", ch1);
   } else {
      printf("%c is not a blank character.", ch1);
   }
   printf("\n");
   if(isblank(ch2)) {
      printf("%c is a blank character.", ch2);
   } else {
      printf("%c is not a blank character.", ch2);
   }
   return 0;
}
```

在这个示例中，我们测试了两个不同的字符，一个是空格字符，另一个是字母字符。如果字符是空格字符，我们打印一条消息表示它是空格字符，否则我们打印一条消息表示它不是空格字符。

isblank()函数是一个典型的C语言函数，用于执行字符分类和操作任务。它可与其他函数，例如isalpha()、isdigit()和isalnum()等一起使用，以执行更复杂的字符操作。

### 1.4 iscntrl()

iscntrl()函数是ctype.h头文件中定义的函数之一，用于测试一个字符是否为控制字符。

控制字符是一些不能显示在屏幕上的字符，常见的控制字符包括制表符、换行符、回车符等等。iscntrl()函数用于测试一个字符是否为控制字符，如果字符是控制字符，则返回非零值（即真），否则返回零（即假）。

以下是一个示例代码：

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char ch1 = '\n';
   char ch2 = 'A';
   if(iscntrl(ch1)) {
      printf("%c is a control character.", ch1);
   } else {
      printf("%c is not a control character.", ch1);
   }
   printf("\n");
   if(iscntrl(ch2)) {
      printf("%c is a control character.", ch2);
   } else {
      printf("%c is not a control character.", ch2);
   }
   return 0;
}
```

在这个示例中，我们测试了两个不同的字符，一个是换行符，另一个是字母字符。如果字符是控制字符，我们打印一条消息表示它是控制字符，否则我们打印一条消息表示它不是控制字符。

iscntrl()函数是C语言中对字符分类和操作功能的一个基本函数之一，通常与其他函数，例如isalpha()、isdigit()和isalnum()等一起使用，以执行更复杂的操作。

### 1.5 isdigit()

在 POSIX 标准中，isdigit()函数是C语言ctype.h头文件中一个用于判断字符是否为数字字符（字符0-9）的函数。如果字符是一个数字，则返回一个非零值（即真），否则返回零（即假）。

示例代码：

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char ch1 = '1';
   char ch2 = 'A';
   if(isdigit(ch1)) {
      printf("%c is a digit character.", ch1);
   } else {
      printf("%c is not a digit character.", ch1);
   }
   printf("\n");
   if(isdigit(ch2)) {
      printf("%c is a digit character.", ch2);
   } else {
      printf("%c is not a digit character.", ch2);
   }
   return 0;
}
```

在这个示例中，我们测试了两个不同的字符，一个是数字字符，另一个是字母字符。如果字符是数字字符，我们打印一条消息表示它是数字字符，否则我们打印一条消息表示它不是数字字符。

总之，isdigit()函数是C语言中用于操作字符的最基本和常用的函数之一，在处理字符和字符串时非常有用。

### 1.6 isgraph()

在 POSIX 标准中，isgraph()函数是C语言ctype.h头文件中的一个函数，用于检查一个字符是否是可打印的图形字符。

具有图形表示的字符是指可以显示在屏幕上的字符，除了空格和控制字符外，所有的字符都属于这个范畴。isgraph()函数会判断一个字符是否是可打印图形字符，如果是，则返回一个非零值（即真），否则返回零（即假）。

下面是一个示例代码：

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char ch1 = '\n';
   char ch2 = 'A';
   if(isgraph(ch1)) {
      printf("%c is a graph character.", ch1);
   } else {
      printf("%c is not a graph character.", ch1);
   }
   printf("\n");
   if(isgraph(ch2)) {
      printf("%c is a graph character.", ch2);
   } else {
      printf("%c is not a graph character.", ch2);
   }
   return 0;
}
```

在这个示例中，我们测试了两个不同的字符，一个是换行符，另一个是字母字符。如果字符是可打印的图形字符，我们打印一条消息表示它是图形字符，否则我们打印一条消息表示它不是图形字符。

总之，isgraph()函数是C语言中用于操作字符的另一个基本函数，在处理字符和字符串时非常有用。和其他ctype.h头文件中的函数，例如isdigit()、isalpha()和isalnum()等一起使用，以执行更复杂的操作。

### 1.7 islower()

islower()函数是C语言ctype.h头文件中的一个函数，用于检查传入的字符是否是小写字母。

如果字符是小写字母，则该函数返回一个非零值（即真），否则返回零（即假）。该函数只检查字符的 ASCII 值，如果字符不是小写字母，则返回假。以下是一个示例代码：

```c
#include <ctype.h>
#include <stdio.h>

int main() {
   char ch1 = 'a';
   char ch2 = 'A';
   if(islower(ch1)) {
      printf("%c is a lowercase letter.", ch1);
   } else {
      printf("%c is not a lowercase letter.", ch1);
   }
   printf("\n");
   if(islower(ch2)) {
      printf("%c is a lowercase letter.", ch2);
   } else {
      printf("%c is not a lowercase letter.", ch2);
   }
   return 0;
}
```

在这个示例中，我们测试了两个不同的字符，一个是小写字母，另一个是大写字母。如果字符是小写字母，我们打印一条消息表示它是小写字母，否则我们打印一条消息表示它不是小写字母。

值得注意的是，另外还有一个 isupper() 函数，它是用来检查一个字符是否是大写字母的，该函数的使用方法和 islower() 函数一样。

在 Python 中，也有一个字符串方法 islower()，用于检查字符串中的所有字母是否都是小写字母。该方法返回一个布尔值，True 表示所有字母都是小写字母，False 则表示至少有一个不是小写字母。

### 1.8 isprint()

略

### 1.9 ispunct()

在 POSIX 标准中，ispunct()是C语言 ctype.h头文件中的一个函数，用于检查传入的字符是否是一个标点符号。 如果字符是标点符号，则该函数返回一个非零值（即真），否则返回零（即假）。

以下是一个示例代码：

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    char c1 = '.';
    char c2 = 'a';

    if (ispunct(c1)) {
        printf("%c is a punctuation mark.\n", c1);
    } else {
        printf("%c is not a punctuation mark.\n", c1);
    }

    if (ispunct(c2)) {
        printf("%c is a punctuation mark.\n", c2);
    } else {
        printf("%c is not a punctuation mark.\n", c2);
    }

   return 0;
}
```

在此示例中，我们使用ispunct()函数测试两个不同的字符，字符'.'是标点符号，而字符'a'不是标点符号。如果字符是标点符号，则打印一条消息表示它是标点符号，否则打印一条消息表示它不是。

总之，ispunct()函数是C语言中用于操作字符的另一个基本函数，在字符串和文本处理中使用非常广泛。和其他ctype.h头文件中的函数，例如isdigit()、isalpha()和isalnum()等一起使用，以执行更复杂的操作。

### 1.10 isspace()

POSIX标准中的 isspace() 函数是一个用于检查一个字符是否为空格字符的函数，它定义在 cctype.h 头文件中。如果字符是空格字符，则该函数返回一个非零值（即真），否则返回零（即假）。

以下是一个在 C++ 中使用 isspace() 函数的示例代码：

```c++
#include <iostream>
#include <cctype>

using namespace std;

int main() {
    char ch = ' ';
    if (isspace(ch)) {
        cout << "该字符是空格\n";
    } else {
        cout << "该字符不是空格\n";
    }
    return 0;
}
```

在这个示例中，我们定义了一个字符变量 ch，然后使用 isspace() 函数检查该字符是否为空格字符。如果检测到该字符是空格字符，则输出一条消息表示该字符是空格字符，否则输出一条消息表示该字符不是空格字符。

在 POSIX 标准中，还包括了用于检查空格字符的 isspace_l() 函数，该函数与 isspace() 函数的功能相同，但可以指定地域设置来检查字符是否为空格字符。

总之，isspace() 函数是 C++ 中用于操作字符的一种基本函数，它可以用来检查一个字符是否为空格字符。

> ps: isspace()相比isblank判断的范围更加广一些

### 1.11 issupper()

在 POSIX C 标准中， issupper() 函数是用于检查一个字符是否为大写字母的函数。该函数定义在 ctype.h 头文件中，并返回一个非零值（即真）或零（即假），表示字符是否是大写字母。此函数仅检查字母字符，而不检查空格、数字或符号。

以下是一个使用 issupper() 函数的示例代码：

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'A';
    if (issupper(ch)) {
        printf("该字符是大写字母\n");
    } else {
        printf("该字符不是大写字母\n");
    }
    return 0;
}
```

这个示例中，我们定义了一个字符变量 ch，然后使用 issupper() 函数检查该字符是否是大写字母。如果该字符是大写字母，则输出一条消息表示该字符是大写字母，否则输出一条消息表示该字符不是大写字母。

总之， issupper() 函数是 POSIX C 标准中用于检查一个字符是否为大写字母的函数，常用于处理字符和文本数据。

### 1.12 isxdigit()

在 POSIX C 标准中，isxdigit() 函数用于检查一个字符是否为十六进制数字字符。该函数定义在 ctype.h 头文件中，并返回一个非零值（即真）或零（即假），表示字符是否为十六进制数字字符。注意，该函数只检查字母字符，不检查空格、数字或符号。

以下是一个使用 isxdigit() 函数的示例代码：

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'A';
    if (isxdigit(ch)) {
        printf("该字符是十六进制数字字符\n");
    } else {
        printf("该字符不是十六进制数字字符\n");
    }
    return 0;
}
```

在这个示例中，我们定义了一个字符变量 ch，然后使用 isxdigit() 函数检查该字符是否为十六进制数字字符。如果该字符是十六进制数字字符，则输出一条消息表示该字符是十六进制数字字符，否则输出一条消息表示该字符不是十六进制数字字符。

总之，在 POSIX C 标准中，isxdigit() 函数是用于检查一个字符是否为十六进制数字字符的函数，常用于处理字符和文本数据。

### 1.13 tolower()

在 POSIX C 标准中，tolower() 函数用于将大写字母转换为相应的小写字母。该函数在 ctype.h 头文件中定义，它接受一个整型参数，表示要转换为小写字母的字符。 返回值是对应的小写字母。如果传递给 tolower() 函数的参数不是大写字母，则函数返回原始字符。

下面是在 POSIX C 中使用 tolower() 函数的示例代码：

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'A';
    char lowercase_ch = tolower((int) ch);
    printf("%c 转换为小写字母是 %c\n", ch, lowercase_ch);
    return 0;
}
```

这段代码将输出 "A 转换为小写字母是 a"， 它就展示了如何将大写字母转换为小写字母。

在问题描述中提到可能会遇到程序崩溃的情况，请注意确保您传递给 tolower() 函数的是正确的参数类型。参数类型必须是整型，而不是字符型。如果传递给该函数的参数是字符型，则必须通过强制转换将其转换为整型，如上面的代码所示。

总之，在 POSIX C 中，tolower() 函数是将大写字母字符转换为小写字母字符的函数，常用于处理文本数据。但在使用该函数时需要注意参数类型的正确性，以避免程序崩溃。

### 1.14 toupper()

在 POSIX C 标准中，toupper() 函数也定义在 ctype.h 头文件中，它接受一个整型参数，表示要转换为大写字母的字符，并返回相应的大写字母。如果传递给 toupper() 函数的参数不是小写字母，则函数返回原始字符。

下面是在 POSIX C 中使用 toupper() 函数的示例代码：



```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'a';
    char uppercase_ch = toupper((int) ch);
    printf("%c 转换为大写字母是 %c\n", ch, uppercase_ch);
    return 0;
}
```

这段代码将输出 "a 转换为大写字母是 A"， 它就展示了如何将小写字母转换为大写字母。

与 tolower() 函数类似，当使用 toupper() 函数时，需要确保传递给该函数的参数类型是整型，而不是字符型。如果传递给该函数的参数是字符型，则必须通过强制转换将其转换为整型。

总之，在 POSIX C 中，toupper() 函数是将小写字母字符转换为大写字母字符的函数，常用于处理文本数据。

## 2 errno.h

### 2.1 errno()

在 C 语言中，errno 是一个由标准 C 库中的头文件 errno.h 定义的全局变量。errno 变量存储着最后一次的错误代码。当通过系统调用或库函数执行操作失败时，errno 变量会被设置为一个非零值，反映导致失败的原因。在这种情况下，程序员可以通过检查 errno 变量的值来了解错误的原因，并采取必要的措施。

在使用 errno 变量时，程序员通常需要获得与 errno 变量对应的错误消息。这可以通过使用 strerror() 函数来实现。strerror() 函数可以将 errno 变量的值作为输入，然后返回一个指向对应错误消息的字符串指针。

以下是一个演示如何使用 errno 变量和 strerror() 函数的示例代码：

```c
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main() {
    FILE *fp = fopen("non-existent-file.txt", "r");
    if(fp == NULL) {
        printf("打开文件失败: %s\n", strerror(errno));
        return 1;
    }
    //...
    fclose(fp);
    return 0;
}
```

在这个示例中，当 fopen() 函数未能打开名为 "non-existent-file.txt" 的文件时，它将返回 NULL 并设置 errno 为 ENOENT。程序员可以使用 strerror() 函数检索该错误，并相应地处理错误情况。在这个示例中，程序员可以从 stderr 输出中读取以下错误消息：

打开文件失败: No such file or directory

因此，将 strerror() 与 errno 结合使用将使应用程序实现更好的错误报告和处理机制。

In conclusion，在 C 语言中，errno 变量是一个重要的变量，提供了一种检查程序中错误发生原因的简便方法，程序员可以通过 strerror() 函数来检索与 errno 变量对应的错误消息。

## 3 fcntl.h

### 3.1 open()

在 POSIX C 中，open() 函数用于打开一个已经存在的文件或者创建一个新的文件。这个函数是一个系统调用，定义在 fcntl.h 头文件中。当打开文件失败时，open() 函数会返回 -1，并且 errno 变量会被设置为一个非零值以指示错误类型。通过检查 errno 变量的值，程序员可以确定打开文件失败的确切原因，并采取适当的措施。

```c
#include <stdio.h> 
#include <fcntl.h>
#include <unistd.h>
#include <errno.h>

int main() { 
	// 打开文件
    int fd = open("tester.txt", O_RDONLY);

	// 检查是否打开成功
    if (fd == -1) {
        perror("Error opening file");
        return 1;
    }
    printf("File opened successfully.\n");

    // 读取文件内容
    char buffer[1024];
    ssize_t bytes_read = read(fd, buffer, sizeof(buffer));
    if (bytes_read == -1) {
        perror("Error reading file");
        close(fd);
        return 1;
    }
    printf("%ld bytes read from file: %s\n", bytes_read, buffer);

    //关闭文件
    int close_result = close(fd);
    if (close_result == -1) {
        perror("Error closing file");
        return 1;
    }
    printf("File closed successfully.\n");

    return 0;
}
```

在这个示例中，open() 函数被用于打开一个名为 tester.txt 的文件。如果打开失败，程序将打印一个错误消息，并返回一个非零值。如果打开成功，则该文件将被用于读取内容。读取完成后，程序将关闭文件，如果未能成功关闭文件，程序将打印一个错误消息。

因此，您可以根据这个示例修改你的代码，确保文件能够成功打开。如果仍然出现问题，程序将打印一个错误消息，指出导致错误的原因。

### 3.2 creat()

在 POSIX C 中，creat() 函数是一个废弃的系统调用，用于创建一个新文件或截断一个已存在的文件。之所以被称为 creat()，而不是 create()，是因为在早期 UNIX 系统中，create() 函数已经被用于创建 FIFO（命名管道），因此创建文件的函数改用了类似的 creat() 名称。

### 3.3 fcntl()

在 POSIX C 中，fcntl() 函数用于对打开的文件描述符进行操作，其中包括如下操作：

- 改变已经打开描述符的属性；
- 获取描述符的属性；
- 复制描述符（比如在父子进程间传递描述符）；
- 加/解锁文件（对于进程间的互斥与同步）。

下面是一个简单的示例代码，演示了如何使用 fcntl() 函数加/解锁文件：

```c
#include <fcntl.h>
#include <stdio.h>
#include <unistd.h>

int main() {
    // 打开文件
    int fd = open("my_file.txt", O_WRONLY);
    if (fd == -1) {
        perror("Error opening file");
        return 1;
    }

    // 加锁文件
    struct flock lock;
    lock.l_type = F_WRLCK;
    lock.l_whence = SEEK_SET;
    lock.l_start = 0;
    lock.l_len = 0;
    if (fcntl(fd, F_SETLK, &lock) == -1) {
        perror("Error locking file");
        close(fd);
        return 1;
    }
    printf("File locked.\n");

    // 写入数据
    char buffer[1024] = "This is some data.\n";
    ssize_t bytes_written = write(fd, buffer, sizeof(buffer));
    if (bytes_written == -1) {
        perror("Error writing to file");
        close(fd);
        return 1;
    }
    printf("%ld bytes written to file.\n", bytes_written);

    // 解锁文件
    lock.l_type = F_UNLCK;
    if (fcntl(fd, F_SETLK, &lock) == -1) {
        perror("Error unlocking file");
        close(fd);
        return 1;
    }
    printf("File unlocked.\n");

    // 关闭文件
    if (close(fd) == -1) {
        perror("Error closing file");
        return 1;
    }

    return 0;
}
```

在这个示例中，fcntl() 函数被用于加锁文件，排他地锁定文件的写入。

### 3.4 posix_fadvise()

posix_fadvise()函数的作用是给内核提供有关应用程序打算如何使用特定文件的提示，以便内核可以相应地优化其行为。该函数使用两个参数：文件描述符和文件中的一个范围。

该函数允许应用程序向内核指定其中一个提示，例如应用程序计划按顺序读取数据，还是只访问文件的某些部分一次。该函数还可以用于建议内核预取或取消缓存文件的某些部分，以预测未来的使用。

在写入大文件时，posix_fadvise()函数可能不太可能对性能产生太大影响。大多数可用的标志与预读取相关而不是写入。但是，有一些一般性的策略可用于优化顺序写入性能，例如将文件分成较大的窗口并使用异步I/O调用将数据写入磁盘。

以下是在C语言中使用posix_fadvise()函数来优化大文件顺序写操作的示例代码：

```c
#include <fcntl.h>
#include <stdio.h>

int main() {
    int fd = open("my_file.txt", O_WRONLY);  // 打开文件
    if (fd < 0) {
        perror("Failed to open file");
        return 1;
    }

    // 建议内核按顺序读取数据
    if (posix_fadvise(fd, 0, 0, POSIX_FADV_SEQUENTIAL) != 0) {
        perror("posix_fadvise failed");
        close(fd);
        return 1;
    }

    // 向文件写入一些数据
    char buffer[1024] = "This is some data.\n";
    ssize_t bytes_written = write(fd, buffer, sizeof(buffer));
    if (bytes_written == -1) {
        perror("Error writing to file");
        close(fd);
        return 1;
    }
    printf("%ld bytes written to file.\n", bytes_written);

    // 关闭文件
    if (close(fd) == -1) {
        perror
    }
```

### 3.5 posix_fallocate()

posix_fallocate() 是一个 POSIX 规范中定义的函数，用于为文件分配空间。它类似于 fallocate() 函数，但有稍微不同的界面。

posix_fallocate() 函数有三个参数：要为其分配空间的文件的文件描述符、开始分配空间的文件内偏移量以及要分配的字节数。当调用 posix_fallocate() 时，它会保留文件的磁盘空间，并将从指定偏移量到（偏移量+长度-1）的字节范围设置为零。

下面是一个使用 posix_fallocate() 函数的例子：

```c
#include <stdio.h>
#include <fcntl.h>
#include <unistd.h>

int main() {
    int fd = open("testfile", O_WRONLY | O_CREAT, 0644);
    if (fd == -1) {
        perror("open");
        return 1;
    }
    off_t offset = 0;
    off_t length = 1024;
    int result = posix_fallocate(fd, offset, length);
    if (result != 0) {
        fprintf(stderr, "posix_fallocate 失败，错误码为 %d\n", result);
        return 1;
    }
    close(fd);
    return 0;
}
```

此代码打开名为 "testfile" 的文件进行写入，然后使用 posix_fallocate() 函数为文件预留 1024 字节的磁盘空间。该过程中，从偏移量 0 开始的字节范围被设置为零。

综上所述，posix_fallocate() 函数用于为文件分配磁盘空间，类似于 fallocate() 函数但有稍微不同的界面。使用 posix_fallocate() 时，分配的空间会自动初始化为零字节。

### 4 fenv.h

### 4.1 feclearexecept()

eclearexecept() 是一个 POSIX c 标准中定义的函数，它用于将指定的浮点异常标志集合置为零。异常指的是出现在浮点运算过程中的错误。

此函数需要一个异常标志集合，用于指定要清除的异常标志。它返回零以表示成功，返回非零值以表示出错。下面是一个使用 eclearexecept() 函数的例子：

```c
#include <stdio.h>
#include <math.h>
#include <fenv.h>

int main() {
    printf("清除之前的浮点异常标志: %d\n", fetestexcept(FE_ALL_EXCEPT));

    double x = sqrt(-1.0);  // 计算平方根，引发无穷大异常

    printf("计算得到的值: %f\n", x);
    printf("清除之前的浮点异常标志: %d\n", fetestexcept(FE_ALL_EXCEPT));

    feclearexcept(FE_ALL_EXCEPT);

    double y = sqrt(-1.0);  // 再次计算平方根，不再引发异常

    printf("计算得到的值: %f\n", y);
    printf("清除之后的浮点异常标志: %d\n", fetestexcept(FE_ALL_EXCEPT));

    return 0;
}
```

在这个例子中，我们使用 sqrt() 函数来计算一个负数的平方根，这会引发浮点异常。我们使用 fetestexcept() 函数来检测异常标志，然后使用 feclearexcept() 函数将异常标志清除。清除标志后，重新计算平方根，发现不再有异常被引发。

总之，eclearexecept() 函数是一种方便的方式来清除浮点异常标志，以便在需要时追踪浮点运算中的错误。

### 4.2 fegetenv()

fegetenv() 函数是 POSIX C 标准中定义的一个函数，可以用来获取调用线程的当前浮点环境。浮点环境包括舍入模式、异常标志和各种控制设置等。

这个函数还接受一个指向 fenv_t 对象的指针，用于存储当前的浮点环境。如果函数执行成功，第二个参数指向的 fenv_t 对象将被初始化为当前的浮点环境。

以下是一个使用 fegetenv() 的示例代码：

```c
#include <stdio.h>
#include <fenv.h>

int main() {
    fenv_t env;
    fegetenv(&env);
    printf("当前的浮点环境：\n");
    printf("  舍入模式：%d\n", (int)fegetround());
    printf("  异常标志：%d\n", (int)feclearexcept(FE_ALL_EXCEPT));
    printf("  控制设置：%d\n", (int)fegetexceptflag((fexcept_t *)&env, FE_ALL_EXCEPT));
    return 0;
}
```

在这个示例中，我们使用 fegetenv() 函数获取当前的浮点环境，并将其存储在变量 "env" 中。然后，我们使用 <fenv.h> 头文件提供的其他功能打印出舍入模式、异常标志和控制设置等信息。

总的来说，fegetenv() 函数可以用于调试浮点错误或其他与浮点算术相关的问题。

## 5 inttypes.h

### 5.1 imaxabs()

imaxabs() 是 POSIX C 标准中定义的一个函数，**用于计算长整型数值的绝对值**。其原型定义如下：

```c
#include <inttypes.h>
intmax_t imaxabs(intmax_t x);
```

其中，参数 x 是要计算绝对值的长整型数值，函数返回 x 的绝对值。

下面是一个使用 imaxabs() 函数的简单示例：

```c
#include <stdio.h>
#include <inttypes.h>

int main() {
    intmax_t x = -1234567890;
    intmax_t y = imaxabs(x);
    printf("x 的绝对值是 %" PRIdMAX "\n", y);
    return 0;
}
```

在上面的例子中，我们将变量 x 设置为 -1234567890，然后使用 imaxabs() 函数计算 x 的绝对值并将结果存储在变量 y 中。最后，我们使用 printf() 函数打印出 y 的值，格式化输出时需要使用 PRIdMAX 宏来指定 printf() 的格式。

总的来说，在需要计算长整型数值的绝对值时，可以使用 imaxabs() 函数来提高代码的可读性和可维护性。

### 5.2 imaxdiv()

imaxdiv() 是 POSIX C 标准中定义的一个函数，用于计算长整型数值的商和余数。其原型定义如下：

```c
#include <inttypes.h>
imaxdiv_t imaxdiv(intmax_t numer, intmax_t denom);
```

其中，参数 numer 是被除数，参数 denom 是除数。函数返回一个名为 imaxdiv_t 的结构体，包含两个成员变量：

- quot：长整型商，即 numer 除以 denom 的结果。
- rem：长整型余数，即 numer 除以 denom 的余数。

下面是一个使用 imaxdiv() 函数的示例：

```c
#include <stdio.h>
#include <inttypes.h>

int main() {
    imaxdiv_t result = imaxdiv(12345, 6789);
    printf("商是 %" PRIdMAX "，余数是 %" PRIdMAX "\n", result.quot, result.rem);
    return 0;
}
```

在这个示例中，我们将被除数设置为 12345，除数设置为 6789，并使用 imaxdiv() 函数计算商和余数。最后，我们使用 printf() 函数格式化输出商和余数。

总的来说，imaxdiv() 函数可以用于计算长整型数值的商和余数，提高代码的可读性和可维护性。

### 5.3 strtoimax

strtoimax() 函数是 POSIX C 标准中定义的一个函数，用于将字符串转换为 intmax_t 类型的带符号整数。如果转换失败，它将返回 0 并将 errno 变量设置为指示错误的代码。但是，"EINVAL" 错误代码在某些平台，包括 Windows 子系统 for Linux (WSL)，上不可用。

如果需要检测无效输入，可以使用 strtol() 函数。该函数在所有平台上都可用，并具有 "EINVAL" 错误代码。但是，这个函数只允许将值转换为 "long" 整数，因此需要进行类型转换将结果转换为 "intmax_t" 值。以下是使用 strtol() 函数检测无效输入的示例代码：

```c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>
#include <inttypes.h>

int main() {
    char *str = "Hello World";
    char *endptr;
    errno = 0;
    long val = strtol(str, &endptr, 10);

    /* 检测各种可能的错误 */
    if (errno == EINVAL) {
        printf("无效输入\n");
    } else if (*endptr != '\0') {
        printf("数字后面有其他字符: %s\n", endptr);
    } else if (val > INTMAX_MAX || val < INTMAX_MIN) {
        printf("值超出 intmax_t 范围\n");
    } else {
        intmax_t result = (intmax_t)val;
        printf("转换后的值: %" PRIdMAX "\n", result);
    }

    return 0;
}
```

在这个示例中，我们使用 strtol() 函数将字符串 "Hello World" 转换为一个 long 整数值。然后，我们检查各种错误条件，例如无效输入或数字后面的其他字符。如果没有检测到错误，我们执行类型转换将结果转换为 "intmax_t" 值，然后使用 printf() 函数打印结果。

## 6 pthread.h

### 6.1 pthread_create()

pthread_create() 函数用于在 POSIX C 的多线程应用程序中创建一个新线程。下面是使用 pthread_create() 函数的示例代码：

```c
#include <pthread.h>
#include <stdio.h>

void *thread_func(void *arg) {
    printf("来自线程 %ld 的问候\n", (long)arg);
    return NULL;
}

int main() {
    pthread_t thread;
    long arg = 42;

    /* 创建新线程 */
    if (pthread_create(&thread, NULL, thread_func, (void *)arg) != 0) {
        fprintf(stderr, "创建线程失败。\n");
        return 1;
    }

    printf("来自主线程的问候。\n");

    /* 等待线程执行结束 */
    pthread_join(thread, NULL);

    return 0;
}
```

在上述示例中，我们使用 pthread_create() 创建了一个新线程。pthread_create() 的第一个参数是一个指向 pthread_t 对象的指针，它将用于标识新线程。第二个参数用于指定线程的各种选项（我们传递 NULL 使用默认选项）。第三个参数是一个指向将由线程执行的函数的指针。最后，第四个参数是将传递给线程函数的参数（在这种情况下，我们传递了 42）。

在创建新线程之后，我们从主线程打印一条消息，然后使用 pthread_join() 等待新线程执行结束。此函数允许主线程等待 pthread_create() 创建的线程完成执行。

总之，pthread_create() 是一个强大而灵活的函数，可以让你在多线程应用程序中创建新线程。

### 6.2 pthread_detach()

pthread_detach() 函数用于将一个线程标记为分离状态，即它将在执行完后自动释放它所分配的系统资源，并且其状态无法被检测。对于已经退出的线程，pthread_join() 函数不能被使用，因为它们在已经分离的状态下不能被重新加入。

在下面的示例代码中，我们将一个线程标记为分离状态，然后使用 pthread_join() 等待它的执行结束：

```c
#include <pthread.h>
#include <unistd.h>

static void *tfunc(void *data) {
    return NULL;
}

int main(int argc, char **argv) {
    pthread_t t;

    /* 创建线程并等待其执行结束 */
    pthread_create(&t, NULL, tfunc, NULL);
    pthread_join(t, NULL);

    /* 将线程标记为分离状态 */
    pthread_detach(t);

    return 0;
}
```

然而这种方法是不正确的。在 POSIX 标准中，pthread_detach() 函数必须在线程仍然连接到进程中时被调用。因此，在线程已经退出的情况下调用 pthread_detach() 是未定义的行为，可能会导致程序崩溃或其他不可预测的结果。

如果您确定一个线程已经退出并且不需要调用 pthread_join() 或者已经在创建线程时将线程标记为分离状态，那么就不需要调用 pthread_detach() 函数。

总之，pthread_detach() 用于将一个线程标记为分离状态，但必须在线程仍然连接到进程中时被调用。

### 6.3 pthread_equal()

在 POSIX C 中，pthread_equal() 函数用于比较两个线程 ID 是否相等。在不同的操作系统中，pthread_t 可能被实现为不同的数据类型，但都指向一个代表线程 ID 的结构体或对象。在一些系统中，pthread_t 甚至可以是指向函数的指针（在这种系统中，线程 ID 是函数地址）。

在 Mac OS X 中，pthread_t 被定义为指向名为 "_opaque_pthread_t" 的结构体的指针。这个结构体是一个不透明的数据类型，因此在应用程序中，我们只能使用 pthread_t 作为一个整体，而不能直接使用它的内部成员。

下面是一个使用 pthread_equal() 函数比较两个线程 ID 是否相等的示例代码：

```c
#include <pthread.h>
#include <stdio.h>
#include <stdbool.h>

void *thread_func(void *arg) {
    printf("Hello from thread.\n");
    return NULL;
}

int main() {
    pthread_t thread1, thread2;

    /* 创建两个新线程 */
    pthread_create(&thread1, NULL, thread_func, NULL);
    pthread_create(&thread2, NULL, thread_func, NULL);

    /* 比较两个线程 ID 是否相等 */
    if (pthread_equal(thread1, thread2)) {
        printf("线程 ID 相等。\n");
    } else {
        printf("线程 ID 不相等。\n");
    }

    /* 等待线程执行结束 */
    pthread_join(thread1, NULL);
    pthread_join(thread2, NULL);

    return 0;
}
```

在这个示例中，我们首先创建了两个新线程，然后使用 pthread_equal() 函数比较它们的线程 ID 是否相等。如果相等，我们将打印一条消息，并在两个线程执行结束后等待它们。

总之，pthread_equal() 函数用于比较两个线程 ID 是否相等，pthread_t 可以在不同的系统中独立定义，但都指向一个代表线程 ID 的结构体.

### 6.4 pthread_exit()

当一个线程在 POSIX C 的多线程应用程序中调用 pthread_exit() 函数时，它将终止自己的执行，并释放与之关联的任何系统资源。 

以下是一个使用 pthread_exit() 函数的示例代码：

```c
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>

void *thread_func(void *arg) {
    int value = 100;
    pthread_exit((void *)value);
}

int main() {
    pthread_t thread;
    void *exit_value;

    /* 创建一个新线程 */
    if (pthread_create(&thread, NULL, thread_func, NULL) != 0) {
        fprintf(stderr, "创建线程失败。\n");
        return 1;
    }

    /* 等待线程执行结束 */
    pthread_join(thread, &exit_value);

    printf("线程退出值为： %d\n", (int)exit_value);

    return 0;
}
```

在这个示例中，我们使用 pthread_create() 函数创建了一个新线程。线程函数 thread_func() 设置了本地整数变量 value 的值为 100，并使用这个值调用 pthread_exit() 函数。

在创建了新线程之后，主线程使用 pthread_join() 函数等待新线程执行完毕。pthread_join() 还允许我们通过传递一个 void 指针来捕获线程的退出值，这个指针将被填充退出值。

在主线程中，我们使用 printf() 函数打印线程的退出值。

总之，pthread_exit() 函数是一个非常有用的函数，它允许线程终止自己的执行并释放与之关联的任何资源。

### 6.5 pthread_join()

创建了一个线程，这个线程以 int 值 100 退出，然后尝试使用 pthread_join() 函数捕获该值。

以下是代码示例：

```c
#include <stdio.h>
#include <pthread.h>

void *doStuff(void *param) {
    int a = 100;
    
    pthread_exit((void *)a);
}

int main() {
    pthread_t tid;
    int exitVal;

    pthread_create(&tid, NULL, doStuff, NULL);
    pthread_join(tid, (void **)&exitVal);

    printf("Exit value: %d\n", exitVal);

    return 0;
}
```

在该示例中，我们使用 pthread_create() 函数创建一个新的线程，并使用 pthread_exit() 函数将整形变量 a 的值设置为 100 并将其作为一个 void 指针返回。在主线程中，我们使用 pthread_join() 函数等待线程执行完毕，并捕获退出值，注意这里必须将 exitVal 指针强制转换为 void * 类型的指针。

最后，我们使用 printf() 函数打印 exitVal 的值。

pthread_join() 函数用于等待线程执行完成，并获取它的退出值。由于 pthread_exit() 函数将 int 类型的值作为 void * 类型返回，我们需要将 exitVal 指针强制转换为 void ** 类型的指针，并在 printf() 函数中使用 %d 格式说明符打印 int 类型的值。

总的来说，pthread_join() 函数是一个重要的工具，用于等待线程完成并获取其退出值。

## 7 sched.h

### 7.1 sched_get_priority_max()

在 POSIX C 中，sched_get_priority_max() 函数用于检索指定策略下可以拥有的最高实时优先级。实时优先级是指在实时调度策略中使用的优先级，这些策略与普通调度策略不同，并且可以支持更高的优先级。

以下是一个使用 sched_get_priority_max() 函数打印系统上可用的最高实时优先级的示例代码：

```c
#include <stdio.h>
#include <sched.h>

int main() {
    int max_priority;
    
    /* 获取系统上的最高实时优先级 */
    max_priority = sched_get_priority_max(SCHED_RR);
    
    /* 打印最高实时优先级 */
    printf("Max real-time priority on this system: %d\n", max_priority);
    
    return 0;
}
```

在这个示例中，我们使用 sched_get_priority_max() 函数来获取 SCHED_RR 调度策略下可用的最高实时优先级，然后使用 printf() 函数打印这个值。

总体而言，sched_get_priority_max() 函数非常有用，因为它允许你知道可以使用的最高实时优先级，这可以帮助你更好地控制你的应用程序的调度和性能。

### 7.2 sched_yield()

这个问题是关于使用 sched_yield() 函数来同步线程的，因为条件变量、锁和信号量的使用受到限制，而只能使用 pthread_create()、pthread_join() 和 sched_yield() 函数。

sched_yield() 函数可用于把正在运行的线程放到等待队列的末尾，强制让其他线程获得 CPU 的执行权。它是一种比较粗糙的同步机制，可以在一个简单的多线程环境中用来防止死锁和过度竞争。

以下是一个使用 sched_yield() 函数实现同步的示例代码：

```c
#include <stdio.h>
#include <pthread.h>

void *threadFunc(void *arg) {
    int id = *(int *)arg;

    /* 让第一个线程优先运行 */
    if (id == 1) {
        sched_yield();
    }

    printf("Thread %d running\n", id);

    return NULL;
}

int main() {
    pthread_t tid1, tid2;
    int id1 = 1, id2 = 2;

    pthread_create(&tid1, NULL, threadFunc, &id1);
    pthread_create(&tid2, NULL, threadFunc, &id2);

    pthread_join(tid1, NULL);
    pthread_join(tid2, NULL);

    return 0;
}
```

在这个示例中，我们使用 pthread_create() 函数创建两个线程，然后令第一个线程优先运行（即在第一个线程中使用 sched_yield() 函数）。在线程执行结束后，我们使用 pthread_join() 函数等待线程的结束。

总之，尽管使用 sched_yield() 函数进行同步是可能的，但这不是一个优雅的解决方案，潜在的问题和限制很多。对于更复杂的问题，推荐使用条件变量、锁和信号量来实现线程同步。

## 8 semaphore.h

### 8.1 sem_init()

sem_init() 是 POSIX 线程库中的一个函数，它用于初始化一个信号量，以进行线程同步和进程间通信。

sem_init() 函数的原型如下：

```c
#include <semaphore.h>

int sem_init(sem_t *sem, int pshared, unsigned int value);
```

其中，sem 是指向要初始化的信号量的指针。pshared 参数指定该信号量是线程内共享还是进程内共享的标志，取值为 0 或非 0。value 参数指定该信号量的初始值。

以下是一个使用 sem_init() 函数初始化信号量的示例代码：

```c
#include <stdio.h>
#include <pthread.h>
#include <semaphore.h>

sem_t my_semaphore;

void * thread_func(void * arg) {
    printf("Waiting for semaphore...\n");

    sem_wait(&my_semaphore);

    printf("Semaphore acquired!\n");

    return NULL;
}

int main() {
    pthread_t thread;

    sem_init(&my_semaphore, 0, 0);

    pthread_create(&thread, NULL, thread_func, NULL);

    printf("Press enter to release semaphore...\n");
    getchar();

    sem_post(&my_semaphore);

    pthread_join(thread, NULL);

    sem_destroy(&my_semaphore);

    return 0;
}
```

在这个示例中，我们创建了一个名为 my_semaphore 的信号量，并指定它为线程内共享的。然后我们创建了一个新线程，该线程等待 my_semaphore 信号量。在主线程中，我们等待用户输入，然后释放该信号量。线程将继续执行，my_semaphore 值被设置为 1。最后，我们销毁了信号量。

总体而言，sem_init() 函数是 POSIX 线程库中非常有用的一个函数，它允许你方便地初始化一个信号量，并用于线程同步和进程间通信。

### 8.2 sem_open()

sem_open() 函数是 POSIX 线程库中的一个函数，它用于打开或创建一个命名的信号量。该函数返回一个表示该信号量的 sem_t 指针，如果发生错误则该指针为 SEM_FAILED。

以下是使用 sem_open() 函数创建一个命名信号量的示例代码：

```c
#include <stdio.h>
#include <semaphore.h>

int main() {
    sem_t *sem;

    /* Open or create the semaphore */
    sem = sem_open("/my_semaphore", O_CREAT, 0644, 0);

    /* Check for errors */
    if (sem == SEM_FAILED) {
        perror("sem_open");
        return 1;
    }

    /* The semaphore is ready to use */

    /* Close the semaphore */
    sem_close(sem);

    /* Unlink the semaphore */
    sem_unlink("/my_semaphore");

    return 0;
}
```

在这个示例中，我们使用 sem_open() 函数创建了一个名为 /my_semaphore 的信号量，并指定它为进程内共享的。然后我们检查 sem_open() 函数是否返回了错误，如果有错误则输出错误信息并返回 1。如果一切顺利，我们可以开始使用信号量。在完成之后，我们调用 sem_close() 函数关闭该信号量，然后使用 sem_unlink() 函数删除该信号量。

总体而言，sem_open() 函数是非常有用的一个函数，它允许你打开或创建一个命名的信号量，并用于进程同步和通信。

### 8.3 sem_post()

sem_post() 是 POSIX 线程库中的一个函数，用于递增信号量的值并唤醒等待该信号量的线程。它通常与 sem_wait() 或 sem_timedwait() 一起使用以实现线程同步和互斥。

在您提供的代码示例中，使用 sem_post() 增加了名为 _TaskCount 的信号量，以通知等待线程任务已经被添加到队列中。而出现 "Invalid argument" 错误可能是由多个原因引起的，如：

- 传递给 sem_post() 的信号量指针无效，例如已经被释放或未初始化。
- 信号量的值已经达到了限制，超过了正常范围。
- 信号量已经被另一个进程的线程占用，无法访问。

为了检查 sem_post() 错误并找出可能的原因，您可以检查返回值和错误号，例如：

```c
if (sem_post(&_TaskCount) == -1) {
    perror("sem_post");
    return 1;
}
```

`perror()` 函数将输出 sem_post() 出现的错误，让您更容易找到问题所在。

综上所述，sem_post() 是一个核心的 POSIX 信号量函数，它用于递增信号量的值并唤醒等待线程。如果在使用时出现错误，可以通过检查返回值和错误号来找出可能的原因，并进行适当的错误处理。

### 8.4 sem_timedwait()

`sem_timedwait()` 是 POSIX 线程库中的函数之一，它等待信号量的值降为 0，这样可以避免使用 `sem_wait()` 函数无限期阻塞线程。不同的是，在等待信号量降为 0 之前，`sem_timedwait()` 允许您在指定的时间段内等待，如果等待超时，它将返回 `ETIMEDOUT` 错误。 

`sem_timedwait()` 的原型如下： 

```c
int sem_timedwait(sem_t *sem, const struct timespec *abs_timeout);
```

其中，`sem` 是指向要等待的信号量的指针， `abs_timeout` 是一个 `timespec` 结构体指针，用于指定等待的时间。

以下是一个示例代码，演示了如何使用 `sem_timedwait()` 函数等待信号量，超时并处理错误：

```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>
#include <semaphore.h>
#include <time.h>

sem_t my_semaphore;

void *thread_func(void *arg) {
    struct timespec ts;
    clock_gettime(CLOCK_REALTIME, &ts);
    ts.tv_sec += 10;  // wait for 10 seconds

    if (sem_timedwait(&my_semaphore, &ts) == -1) {
        if (errno == ETIMEDOUT) {
            printf("Thread timed out waiting for semaphore\n");
        } else {
            perror("sem_timedwait");
        }
    } else {
        printf("Thread acquired semaphore!\n");
        sem_post(&my_semaphore);
    }

    return NULL;
}

int main() {
    pthread_t thread;

    if (sem_init(&my_semaphore, 0, 1) == -1) {
        perror("sem_init");
        return 1;
    }

    if (pthread_create(&thread, NULL, thread_func, NULL) == -1) {
        perror("pthread_create");
        return 1;
    }

    sleep(5); // wait for 5 seconds

    sem_post(&my_semaphore);
    pthread_join(thread, NULL);

    sem_destroy(&my_semaphore);

    return 0;
}

```

### 8.5 sem_wait()

`sem_wait()` 是 POSIX 线程库中的一个函数，它用于等待信号量的值降为 0（即等待减少信号量的操作）。它会阻塞当前线程直至成功地降低信号量的值。如果在等待期间收到信号，则可能会导致函数被中断，但是这取决于信号处理程序的设置。

```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>
#include <semaphore.h>
#include <signal.h>

sem_t my_semaphore;

void signal_handler(int signum) {
    sem_post(&my_semaphore);
}

int main() {
    // Set up signal handling for SIGINT
    struct sigaction sa;
    sa.sa_handler = signal_handler;
    sigemptyset(&sa.sa_mask);
    sa.sa_flags = 0;
    sigaction(SIGINT, &sa, NULL);

    if (sem_init(&my_semaphore, 0, 0) == -1) {
        perror("sem_init");
        return 1;
    }

    printf("Waiting for semaphore...\n");

    // Wait for semaphore
    if (sem_wait(&my_semaphore) == -1) {
        perror("sem_wait");
        return 1;
    }

    printf("Semaphore acquired!\n");

    sem_destroy(&my_semaphore);

    return 0;
}
```

### 8.6 sem_close()

`sem_close()` 是 POSIX 信号量函数族中的一个函数，用于关闭指向已命名信号量的标识符。当不再需要访问该信号量时，应使用 `sem_close()` 函数关闭该信号量。

以下是一个示例代码，演示了如何使用 `sem_open()`、`sem_close()` 和 `sem_destroy()` 函数来管理已命名的信号量：

```c
#include <stdio.h>
#include <stdlib.h>
#include <semaphore.h>
#include <fcntl.h>

int main() {
    sem_t *my_semaphore;

    // Create named semaphore
    my_semaphore = sem_open("/my_semaphore", O_CREAT, 0644, 1);
    if (my_semaphore == SEM_FAILED) {
        perror("sem_open");
        return 1;
    }

    // Use semaphore...

    // Close named semaphore
    if (sem_close(my_semaphore) == -1) {
        perror("sem_close");
        return 1;
    }

    // Destroy named semaphore
    if (sem_unlink("/my_semaphore") == -1) {
        perror("sem_unlink");
        return 1;
    }

    return 0;
}
```

在这个示例中，我们使用 `sem_open()` 函数创建了一个名为 `/my_semaphore` 的信号量，并将其初始化为值 1。我们使用 `sem_close()` 函数在完成对该信号量的使用后关闭该信号量。最后，我们使用 `sem_unlink()` 函数来销毁该信号量。

需要注意的是，`sem_close()` 函数不会销毁信号量，而是关闭指向信号量的标识符。如果要销毁该信号量，需要使用 `sem_unlink()` 函数。

### 8.7 sem_destory()

`sem_destroy()` 函数是 POSIX 信号量函数族中的一个函数，用于销毁一个使用 `sem_init()` 或 `sem_open()` 创建的信号量。一旦信号量被销毁，它就不能再使用了。

该函数在 POSIX 规范中并未被标记为过时，但在苹果 macOS 平台上提供的实现中被标记为过时。这可能是因为苹果引入了一种更新的信号量实现方式，希望开发者使用这种新的实现方式，而不是依赖于 POSIX 实现方式。

在 macOS 上，`sem_destroy()` 的替代方法是 `dispatch_semaphore_t` 类型及其对应的 Grand Central Dispatch (GCD) 库中的函数，例如 `dispatch_semaphore_create()` 和 `dispatch_release()`。该库提供了一种特定于 macOS 和 iOS 系统的并发处理替代 API，被认为是比旧的 POSIX 实现更现代化和高效的方法。

### 8.8 sem_getvalue()

该代码使用了 POSIX 信号量函数族中的 `sem_init()` 和 `sem_getvalue()` 函数，并尝试获取已初始化的信号量的值并将其打印出来。但是，无论如何，它都打印出了 0。原因是此代码使用了未命名的信号量，而 `sem_getvalue()` 函数无法正确获取未命名信号量的值。

未命名的信号量只能在当前进程内使用，并且不带名称。相反，已命名的信号量可以跨多个进程和主机使用，并且带有名称。对于未命名信号量，应使用 `sem_destroy()` 函数在使用完信号量后释放其资源。

以下是一个可以正确打印值的示例代码，使用已命名的信号量：

```c
#include <stdio.h>
#include <stdlib.h>
#include <semaphore.h>

int main() {
    sem_t *my_semaphore;
    int value;

    // Create named semaphore
    my_semaphore = sem_open("/my_semaphore", O_CREAT, 0644, 1);
    if (my_semaphore == SEM_FAILED) {
        perror("sem_open");
        return 1;
    }

    // Get value of semaphore
    sem_getvalue(my_semaphore, &value);
    printf("Semaphore value: %d\n", value);

    // Close named semaphore
    if (sem_close(my_semaphore) == -1) {
        perror("sem_close");
        return 1;
    }

    // Destroy named semaphore
    if (sem_unlink("/my_semaphore") == -1) {
        perror("sem_unlink");
        return 1;
    }

    return 0;
}
```

在此示例中，我们使用 `sem_open()` 函数创建了一个名为 `my_semaphore` 的已命名信号量，并将其初始化为值 1。我们使用 `sem_getvalue()` 函数获取该信号量的值，然后使用 `sem_close()` 函数关闭该信号量并使用 `sem_unlink()` 函数销毁该信号量。

需要注意的是，使用信号量时应该非常小心，以避免死锁。

## 9 time.h

### 9.1 ctime()

ctime()是一个POSIX C库函数，用于将时间戳转换为可读的日期和时间格式。它接受一个time_t参数，该参数表示从1970年1月1日UTC（协调世界时）以来的秒数，返回一个指向静态字符串的指针，其中包含可读的日期和时间信息。

以下是一个示例程序，演示如何使用ctime()函数：

```c
#include <stdio.h>
#include <time.h>

int main(void) {
    // 获取当前时间戳
    time_t current_time = time(NULL);

    // 将时间戳转换为可读格式
    char* readable_time = ctime(&current_time);

    // 输出可读时间格式
    printf("当前时间： %s", readable_time);

    return 0;
}
```

这个程序将当前的时间戳转换为可读格式，并输出到控制台。在这个示例中，将会输出当前的日期和时间，例如"Fri Nov 19 15:24:23 2021"。

总之，ctime()函数在POSIX C库中用于将时间戳转换为可读的日期和时间格式，可以帮助开发人员对日期和时间进行格式化处理和输出。

### 9.2 localtime()

localtime()是一个POSIX C库函数，用于将time_t时间类型的日期和时间转换为struct tm结构体表示的本地日期和时间格式。它接受一个time_t参数，表示从1970年1月1日UTC（协调世界时）以来的秒数，并返回一个struct tm结构体，其中包含本地日期和时间信息。

以下是一个示例程序，演示如何使用localtime()函数：

```c
#include <stdio.h>
#include <time.h>

int main(void) {
    // 获取当前时间戳
    time_t current_time = time(NULL);

    // 将当前时间戳转换为本地时间
    struct tm* local_time = localtime(&current_time);

    // 输出本地时间
    printf("当前本地时间：%d-%02d-%02d %02d:%02d:%02d\n", 
        local_time->tm_year + 1900, local_time->tm_mon + 1, local_time->tm_mday, 
        local_time->tm_hour, local_time->tm_min, local_time->tm_sec);

    return 0;
}
```

这个程序将当前的时间戳转换为本地时间，并输出到控制台。在这个示例中，将会输出当前的本地日期和时间，例如"2021-11-19 23:22:01"。

需要注意的是，本地时间的计算依赖于操作系统的时区设置，而且在进程起动时会以此来进行一次性计算，并保存在系统内部。因此，若在程序运行期间改变了时区设置，并不能立即对使用localtime()计算所产生的结果进行同步更新。如果需要更新时区设置，可以调用tzset()函数来重新计算。

总之，localtime()函数在POSIX C库中用于将time_t时间类型的日期和时间转换为struct tm结构体表示的本地日期和时间格式，可以帮助开发人员对日期和时间进行格式化处理和输出。

### 9.3 time()

time()是一个POSIX C库函数，用于获取当前系统时间（从1970年1月1日UTC（协调世界时）以来的秒数）并将其返回给调用方。它不接受任何参数，而是直接返回一个time_t类型的值。它通常用作其他时间相关函数的输入，比如localtime()、strftime()等。

以下是一个示例程序，演示如何使用time()函数：

```c
#include <stdio.h>
#include <time.h>

int main(void) {
    // 获取当前系统时间
    time_t current_time = time(NULL);

    // 输出当前系统时间
    printf("当前系统时间戳：%ld\n", current_time);

    return 0;
}
```

这个程序将获取当前的系统时间戳，并将其输出到控制台。

总之，time()函数在POSIX C库中用于获取当前系统时间（从1970年1月1日UTC（协调世界时）以来的秒数），通常用作其他时间相关函数的输入。它可以帮助开发人员对日期和时间进行格式化处理和输出。

### 9.4 clock()

clock()是一个POSIX C库函数，用于返回程序运行的CPU时间。它不接受任何参数，并返回一个clock_t类型的数值，即程序在执行过程中消耗的时钟数，从而可以测量程序的性能和运行时间。

需要注意的是，clock()并不是系统时间，而是在程序执行过程中所花费的CPU时间。因此，与时间相关的库函数，如ctime()、localtime()等，不能使用clock()函数获取系统时间，而应该使用time()函数。

以下是一个示例程序，演示如何使用clock()函数：

```c
#include <stdio.h>
#include <time.h>

int main(void) {
    // 记录程序开始时间
    clock_t start_time = clock();

    // 模拟程序运行
    for (int i = 0; i < 1000000000; i++);

    // 记录程序结束时间
    clock_t end_time = clock();

    // 计算消耗的CPU时间
    double cpu_time_used = ((double) (end_time - start_time)) / CLOCKS_PER_SEC;

    // 输出CPU时间
    printf("程序使用CPU时间：%f 秒\n", cpu_time_used);

    return 0;
}
```

这个程序将记录程序的开始时间和结束时间，并计算程序的消耗CPU时间，并输出到控制台。在这个示例中，将会输出程序消耗的CPU时间，例如"程序使用CPU时间：0.019487 秒"。

总之，clock()函数在POSIX C库中用于返回程序在执行过程中消耗的CPU时间，可以帮助开发人员测量程序的性能和运行时间。

## 10 mqueue.h

### 10.1 mq_open()

mq_open()是一个POSIX C库函数，用于创建或打开一个POSIX消息队列。它接受一个消息队列名称和一组标记作为输入，并返回一个mqd_t类型的值，表示消息队列的描述符。如果消息队列尚不存在，则可以使用O_CREAT标记来创建它。如果消息队列已经存在，使用O_RDWR标记打开以进行读写访问。如果使用O_RDONLY标记，则打开消息队列以进行只读访问。

以下是一个示例程序，演示如何使用mq_open()函数：

```c
#include <stdio.h>
#include <stdlib.h>
#include <mqueue.h>
#include <fcntl.h>

int main() {
    mqd_t mqd;
    struct mq_attr mqattr;
    char *queueName = "/my_queue";  // 设置消息队列名称

    mq_unlink(queueName);          // 确保消息队列不存在
    mqattr.mq_flags   = 0;          // 默认标记
    mqattr.mq_maxmsg  = 10;         // 最大消息数量
    mqattr.mq_msgsize = BUFSIZ;     // 消息最大字节数
    mqd = mq_open(queueName, O_CREAT | O_EXCL | O_RDWR, 0666, &mqattr); // 创建一个新的消息队列

    if (mqd < 0) {
        perror("mq_open failed");
        exit(1);
    }
    printf("mqd:%d\n", mqd);       // 输出描述符
    mq_close(mqd);                 // 关闭消息队列
    mq_unlink(queueName);          // 删除消息队列

    return 0;
}
```

这个程序将创建一个名为"/my_queue"的新消息队列，并获取其描述符mqd。然后，它将关闭消息队列，并清除它。

总之，mq_open()函数在POSIX C库中用于创建或打开一个POSIX消息队列，并返回消息队列的描述符。它可以帮助开发人员实现进程间通信和线程间通信等高级功能。

### 10.2 mq_send()

在POSIX IPC中，mq_send()函数只能发送char类型的数据，无法发送结构体等其他类型的数据。但是，您可以将结构体转换为char数组，然后使用mq_send()函数发送它。接收进程可以使用mq_receive()函数接收消息并将其转换回原始结构体类型。

下面是一个示例程序，演示如何将自定义结构体发送到消息队列中，并使用mq_receive()函数接收它：

```c
#include <stdio.h>
#include <stdlib.h>
#include <mqueue.h>
#include <string.h>

typedef struct {
    pid_t pid;
    char data[4096];
} Req;

int main() {
    mqd_t mqd;
    struct mq_attr mqattr;
    char *queueName = "/my_queue";
    Req req = {getpid(), "Hello, world!"};

    // create a message queue
    mq_unlink(queueName);
    mqattr.mq_flags   = 0;
    mqattr.mq_maxmsg  = 10;
    mqattr.mq_msgsize = sizeof(Req);
    mqd = mq_open(queueName, O_CREAT | O_EXCL | O_RDWR, 0666, &mqattr);

    // send a message containing a struct
    if (mq_send(mqd, (char *)&req, sizeof(Req), 0) == -1) {
        perror("mq_send");
        exit(EXIT_FAILURE);
    }

    // receive the message and print its contents
    Req recv_req;
    if (mq_receive(mqd, (char *)&recv_req, sizeof(Req), NULL) == -1) {
        perror("mq_receive");
        exit(EXIT_FAILURE);
    }
    printf("Received message: pid=%d, data=%s\n", recv_req.pid, recv_req.data);

    // cleanup
    mq_close(mqd);
    mq_unlink(queueName);

    return 0;
}
```

在这个例子中，我们创建了一个名为"/my_queue"的消息队列，并定义了一个名为Req的自定义结构体。使用结构体Req将当前进程ID和一个字符串封装在一起。然后，我们使用mq_send()函数将该结构体发送到消息队列中。

### 10.3 mq_receieve()

mq_receive()是一个POSIX C库函数，用于从消息队列中接收消息。它需要接收一个mqd_t类型的消息队列描述符、一个char指针以及指定消息大小的size_t类型的字节数，并返回实际接收的字节数。如果消息队列中没有消息可供接收，则将阻塞调用线程，直到消息可用。

以下是一个示例程序，演示如何使用mq_receive()函数接收消息：

```c
#include <stdio.h>
#include <stdlib.h>
#include <mqueue.h>
#include <string.h>

int main() {
    mqd_t mqd;
    struct mq_attr mqattr;
    char *queueName = "/my_queue";
    char buf[1024];

    mq_unlink(queueName);
    mqattr.mq_flags   = 0;
    mqattr.mq_maxmsg  = 10;
    mqattr.mq_msgsize = 1024;
    mqd = mq_open(queueName, O_CREAT | O_EXCL | O_RDWR, 0666, &mqattr);
    if (mqd == (mqd_t)-1) {
        perror("mq_open");
        exit(EXIT_FAILURE);
    }

    // send a message to the queue
    if (mq_send(mqd, "Hello, world!", sizeof("Hello, world!"), 0) == -1) {
        perror("mq_send");
        exit(EXIT_FAILURE);
    }

    // receive the message from the queue
    ssize_t numBytes;
    if ((numBytes = mq_receive(mqd, buf, sizeof(buf), NULL)) == -1) {
        perror("mq_receive failed");
        exit(EXIT_FAILURE);
    }
    buf[numBytes] = '\0';
    printf("Received message: %s\n", buf);

    // cleanup and exit
    mq_close(mqd);
    mq_unlink(queueName);
    return 0;
}
```

在这个例子中，我们创建了一个名为"/my_queue"的消息队列，并在其中发送了一个字符串。然后，我们使用mq_receive()函数从队列中接收该消息，并将其打印出来。

### 10.4 mq_unlink()

当您完成使用 POSIX 消息队列时，您应该首先使用 mq_close() 函数关闭消息队列，以释放消息队列在使用的任何资源，并允许其他进程在必要时访问它。然后，您可以使用 mq_unlink() 函数从系统中删除消息队列。这将永久删除消息队列并防止对其进行进一步访问。

以下是使用 mq_unlink() 删除消息队列的例子：

```c
#include <stdio.h>
#include <stdlib.h>
#include <mqueue.h>

int main() {
    mqd_t mqd;
    char *queueName = "/my_queue";

    // 创建消息队列
    mq_unlink(queueName);
    mqd = mq_open(queueName, O_CREAT | O_EXCL | O_RDWR, 0666, NULL);

    // 关闭并删除消息队列
    mq_close(mqd);
    mq_unlink(queueName);

    return 0;
}
```

该例子首先使用 mq_unlink() 删除任何具有相同名称的消息队列。然后，我们使用指定的名称和权限使用 mq_open() 创建了一条新的消息队列。一旦我们使用消息队列完毕，我们使用 mq_close() 关闭它，并使用 mq_unlink() 从系统中删除它。

请注意，一旦您使用 mq_unlink() 删除消息队列，任何尝试使用相同队列名称的 mq_open() 都将失败，并显示 ENOENT 的错误代码。

