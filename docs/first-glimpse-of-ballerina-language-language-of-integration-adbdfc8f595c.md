# 芭蕾舞女演员语言一瞥:融合的语言

> 原文：<https://medium.com/hackernoon/first-glimpse-of-ballerina-language-language-of-integration-adbdfc8f595c>

![](img/29a36626354a34e46596941cb4aa4dab.png)

> 这篇博客中给出的源代码是芭蕾舞女演员 1.x 系列的参考。请遵循芭蕾舞演员天鹅湖发布的最新文件。

Ballerina 是今年 9 月 10 日发布的最新编程语言。外面有一千多种编程语言。为什么需要另一种编程语言？芭蕾舞语言旨在简化被称为集成的特定编程领域。您可能是一名开发不同类型的 web 服务并打算将这些服务互连起来的开发人员。那么芭蕾舞语言将是你的下一个编程伴侣。

这篇文章旨在向您介绍 Ballerina，这是一种灵活、强大而美丽的编程语言，可以帮助您实现任何类型的集成需求。您可以从官方 [Ballerinalang](https://ballerina.io/downloads/) 网站下载并安装 Ballerina。

# 它看起来像什么？

当我说这是一种编程语言时，您首先想到的是它的外观。芭蕾舞演员语言语法是基于 Java、Go 和 JavaScript 等编程语言形成的。芭蕾舞演员是一种静态类型的语言。Ballerina 将 nil、boolean、int、float、decimal 和 string 作为基本数据类型。例如，如果需要定义一个整数，语法如下。

int total = 99

与其他语言一样，芭蕾舞演员使用 main 方法，这是主要的程序入口点。您可以编写一个简单的“hello world ”,如下所示。

```
import ballerina/io;public function main() {
    io:println("Hello, World!");
}
```

除了常规的原始数据类型，Ballerina 还提供了各种非原始数据类型，如数组、元组、映射、表、联合等。芭蕾舞演员用括号“()”表示零

另一种特殊类型变量是“anydata”数据类型。该类型是`()|boolean|int|float|decimal|string|(anydata|error)[]|map<anydata|error>|xml|table`数据类型的并集。anydata 变量可以用在需要纯值的地方。

由于 Ballerina 专门设计用于构建在网络上运行的应用程序，它本身就支持 JSON 和 XML。在 JavaScript 中，您可以轻松地将 JSON 变量定义为如下形式。

```
json user = {
         fname: "Peter",
         lname: "Stallone",
         "age": age,
         address: {
             line: "20 Palm Grove",
             city: "Colombo 03",
             country: "Sri Lanka"
         }
    };
io:println(user.address.country);
```

同样，您也可以定义 XML 对象并与之交互。

```
xml x1 = xml `<book>The Lost World</book>`;
io:println(x1);
```

Ballerina 提供内置库来实现不同类型的功能。在芭蕾舞中，这些被称为模块。模块的工作方式与 Java 包相同。您可以将内置模块或自己的模块导入到应用程序中。芭蕾舞演员有内置的日志，数学，编码，字符串，缓存，时间，文件处理，以及更多的模块。

语法的流控制与其他语言相同。它支持语法“if else”、“while”和“foreach”Foreach 语法提供了对数组和映射的迭代支持。如果您正在寻找一种有吸引力的方法来验证 null，那么 Ballerina 将把交给 Elvis 操作符来验证指定的变量是否为 null。语法应该是“表达式”。:expressionIfNil '以及下面验证变量 x 是否为空的示例。

```
string elvisOutput = x ?: "value is nil";
```

# 芭蕾舞演员的面向对象编程

Ballerina 确实为面向对象编程提供了帮助。芭蕾舞演员 OOP 语法似乎更接近 Python OOP 语法。下面是一个用构造函数定义对象的例子。

```
type Person object {
    public int age;
    public string firstName;
    public string lastName;

    function __init(int age, string firstName, string lastName) {
        self.age = age;
        self.firstName = firstName;
        self.lastName = lastName;
    }

    function getFullName() returns string {
        return self.firstName + " " + self.lastName;
    }

    function checkAndModifyAge(int condition, int a);
};

function Person.checkAndModifyAge(int condition, int a) {

    if (self.age < condition) {
        self.age = a;
    }
}
```

实例化对象简单明了，就像“Person p1 = new(5，“John”，“Doe”)；”。对象可以用点(“.”来访问)运算符，它与其他语言中的运算符相同。

```
p1.getFullName()
```

芭蕾舞演员为封装提供帮助。在这里，您可以在具有适当访问级别的对象中定义变量。Ballerina 支持以下访问修饰符。

*   公共—随处可见
*   私有—仅在同一对象中可见
*   无修饰符—仅在同一包中可见。

你也可以在芭蕾舞演员身上运用抽象概念。抽象是一个强大的 OOP 概念，在大型模块化软件的设计中是必不可少的。您可以在 ballerina 中定义和重用抽象对象。您可以使用 abstract 关键字将对象转换为抽象对象。抽象对象的例子如下。

```
type Person abstract object {
    public int age;
    public string firstName;
    public string lastName;

    function getFullName() returns string;

    function checkAndModifyAge(int condition, int a);
};
```

您可以如下重用“Person”对象，以重用 Person 对象中的变量和方法。

```
type Employee abstract object {

    *Person;    
    public float salary;

    function __init(int age, string firstName, string lastName) {
        self.age = age;
        self.firstName = firstName;
        self.lastName = lastName;
    }
    function getSalary() returns float;

};
```

还有一个剩余的 OOP 概念，称为多态性，以完成芭蕾舞演员语言中的 OOP 概念。多态性也可以在芭蕾舞演员语言中实现，如前面的代码段所示。这里，person 对象可以有许多类型，因为它是一个抽象类。

```
Person p = new Employee(5, "John", "Doe");
```

# 融入芭蕾舞语言

正如我在前面的介绍中提到的，Ballerina 是专门为解决整合问题而设计的。我们生活在一个地球上，成千上万的网络服务器正在运行并相互交流。早期的开发人员在连接这些服务时遇到了问题。企业集成总线作为集成问题的解决方案应运而生。ESB 模型提供了一种优雅的方式来将不同种类的服务相互连接起来。这些 ESB 产品的共同问题是难以配置且灵活性较差。

与 ESB 相比，Ballerina 更加用户友好，因此开发人员可以通过编码来设计系统。芭蕾舞演员提供内置库来解决各种集成问题。

集成的一般要求是在不同的协议之间读取、转发和转换消息。Ballerina 为 HTTP、HTTPS、HTTP2、Websockets、GRPC、TCP、UDP 等传输提供内置的帮助。

芭蕾舞演员既可以充当客户，也可以充当服务器。向另一个端点发送请求很简单，因为它只需要三行代码。通过根据需要设置请求头，您可以轻松地调用 REST API 后端。由于 Ballerina 原生支持 JSON，所以您可以直接在软件中操作 JSON 内容，而无需从第三方导入模块。

```
import ballerina/http;
http:Client clientEndpoint = new("https://postman-echo.com");
public function main() {
    var response = clientEndpoint->get("/get?test=123");
}
```

另一方面，你可以用芭蕾舞语言创建一个 HTTP 服务器。您可以使用内置的安全功能来保护您的 HTTPS 链接。

```
import ballerina/http;
import ballerina/log;
http:ServiceEndpointConfiguration helloWorldEPConfig = {
    secureSocket: {
        keyStore: {
            path: "${ballerina.home}/bre/security/ballerinaKeystore.p12",
            password: "ballerina"
        }
    }
};

listener http:Listener helloWorldEP = new(9095, config = helloWorldEPConfig);

@http:ServiceConfig {
    basePath: "/hello"
}
service helloWorld on helloWorldEP {
    @http:ResourceConfig {
        methods: ["GET"],
        path: "/"
    }
    resource function sayHello(http:Caller caller, http:Request req) {
        var result = caller->respond("Hello World!");
        if (result is error) {
            log:printError("Error in responding ", err = result);
        }
    }
}
```

Ballerina 还通过 HTTP 接口提供流支持。构建基于 GRPC 和 web 套接字的服务器就像构建 HTTP 服务器一样简单直接。

就可靠的消息传递而言，消息代理是集成最重要的方面之一。如果您需要可靠地发送消息，您可以将消息代理与 Ballerina Integrator 一起使用。芭蕾舞女演员为 ActiveMQ、RabbitMQ 和 NATS 等著名的消息代理提供帮助。您可以只使用几行芭蕾舞演员代码来生成和接收消息，这使它成为满足所有集成要求的最佳语言。

# 结论

在这篇文章中，我试图解释 Ballerina 作为一种通用编程语言以及一种专门的集成编程语言的能力。还有很多特性，比如线程、流、安全性和对微服务的本地支持，我在这里没有提到。我将在另一篇文章中向您详细解释这些特性。

你可以从他们的官方网站了解更多关于芭蕾舞语言的信息。在那里，您可以找到每个用例的示例实现。你可以在[推特](https://hashnode.com/draft/5d6409eddbe38ab2541a210d)上关注我，了解更多关于科技的东西。前往芭蕾舞演员[下载](https://ballerina.io/downloads/)页面，立即试用。顾名思义，它灵活、强大、美观。

![](img/43c735f65292db8fa44da92c747706cf.png)

[现在你可以在亚马逊上预订芭蕾舞书的云原生应用。点击此处预购该书。](https://www.amazon.com/-/en/Dhanushka-Madushan-ebook/dp/B0912GTBPQ/)