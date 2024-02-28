### note 1
每条语句以分号结尾

### note 2
大多数系统中，main的返回值被用来指示状态，0表示成功，非0的返回值有系统定义，通常用来指示错误类型。这是一种设计规范。

### note 3
编译器会忽略注释的内容，因此注释对代码性能没有影响

### 练习1.3 便携程序，在标准输出上打印Hello, World

```
#include <iostream>

int main() {
    std::cout << "Hello World." << std::endl;
    return 0;
}
```

### 练习1.6 
不合法， 会有编译错误. 解决方法是把分号去掉

### 练习1.7
```
std::cout << "/*";  // ok
std::cout << "*/";  // ok
std::cout << /* "*/" */  // 不合法, 注释的结尾是最左匹配的
std::cout << std::cout << /* "*/" /* "/*" */  // 合法，注释还是最近匹配的
```

### 练习1.9
```
#include <iostream>

int main() {
    int val = 50;
    int sum = 0;
    while (val < 101) {
        sum += val;
        val++;
    }

    std::cout << "Sum of 50 ~ 100 is " << sum << std:: endl; 
    return 0;
}
```

### 练习1.10
```
#include <iostream>

int main() {
    int val = 10;
    while (val > 0) {
        std::cout << val << std::endl;
        val--;
    }

    return 0;
}
```

### 练习1.11
```
#include <iostream>

int main() {
    int val1 = 0, val2 = 0;
    std::cout << "input 2 number" << std::endl;
    std::cin >> val1 >> val2;
    // 假设 val1 > val2, 这里可以做个逻辑来兼容。这里就省略了
    while(val1 > val2) {
        std::cout << val1 << std::endl;
        val1--;
    }
    std::cout << val1;

    return 0;
}

```

### 练习1.12
最终结果是0, ++运算符也是等循环体执行结束以后才会起作用。

### 练习1.13

```
#include <iostream>

int main() {
    int sum = 0;
    for (int i = 50; i <= 100; i++) {
        sum += i;
    }

    std::cout << sum;
    return 0;
}
======================================
#include <iostream>

int main() {
    for (int i = 10; i > 0; i--) {
        std::cout << i << std::endl;
    }
    return 0;
}
======================================
#include <iostream>

int main() {
    int val1 = 0, val2 = 0;
    std::cout << "input 2 number" << std::endl;
    std::cin >> val1 >> val2;
    // 假设 val1 > val2, 这里可以做个逻辑来兼容。这里就省略了
    for (val1; val1 >= val2; val1--) {
        std::cout << val1 << std::endl;
    }
    std::cout << val1;

    return 0;
}

```