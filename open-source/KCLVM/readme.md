# KCLVM

KCLVM（Kusion Configuration Language Virtual Machine）是云原生可编程技术栈 Kusion 的核心组成部分，是 KCL 配置语言编译器前后端实现的统称，用于编译 KCL 配置文件并产生相应的 YAML/JSON 配置。此外 KCL 是一种专用于配置定义、校验的动态强类型配置语言，重点服务于云原生基础设施配置和策略定义场景，即基础设施代码化 IaC（Infrastructure as Code）和策略代码化 PaC（Policy as Code）。

## 介绍

Kusion 配置语言（KCL）是一个开源的基于约束的记录及函数语言。KCL 通过成熟的编程语言理论和实践来改进对大量繁杂的配置数据和逻辑的编写，通过声明式的语法结合静态类型等技术特性来简化和校验配置的开发和运维工作。

## 特性

+ **设计优良**：独立设计的语法、语义、运行时和系统库，提供配置（config）、类型（schema）、函数（lambda）、规则（rule）等核心语言元素
+ **建模能力**：以 Schema 为中心的建模抽象
+ **使用简单**：语言自身覆盖大多数配置和策略功能
+ **可靠**：静态类型系统和自定义 Rule 规则约束
+ **可扩展**：配置分块定义能力及丰富的配置合并覆盖能力
+ **自动化能力**：丰富的语言级 CRUD API 和多语言 API
+ **高性能**：语言编译器本身采用 Rust & C 实现，配合 LLVM 优化器，支持编译到本地代码和 WASM 等格式并高效执行
+ **云原生亲和**：原生支持 [OpenAPI](https://github.com/KusionStack/kcl-openapi) 和 Kubernetes CRD Specs 到 KCL 的转换，支持 Kubernetes YAML 规范
+ **开发友好**：丰富的语言工具 (Lint，Test，Vet，Doc 等)、 [IDE 插件](https://github.com/KusionStack/vscode-kcl)和[语言插件](https://github.com/KusionStack/kcl-plugin)

## 场景

您可以将 KCL 用于

+ 生成低级配置数据如 JSON, YAML 等
+ 使用 schema 对配置数据进行建模并减少配置数据中的样板文件
+ 为配置数据定义带有规则约束的 schema 并对数据进行自动验证
+ 分块编写配置数据并使用不同的策略合并数据
+ 无副作用地组织、简化、统一和管理庞大的配置
+ 与 [Kusion Stack](https://kusionstack.io) 一起，定义您的应用交付运维生态

## 安装

从 Github releases 页面[下载](https://github.com/KusionStack/KCLVM/releases)，并且将 `{install-location}/kclvm/bin` 添加到您的环境变量中

## 快速开始

`./samples/fib.k` 是一个计算斐波那契数列的例子

```kcl
schema Fib:
    n1: int = n - 1
    n2: int = n1 - 1
    n: int
    value: int
    if n <= 1:
        value = 1
    elif n == 2:
        value = 1
    else:
        value = Fib {n: n1}.value + Fib {n: n2}.value
fib8 = Fib {n: 8}.value
```

我们可以通过执行如下命令得到 YAML 输出

```
kcl ./samples/fib.k
```

YAML 输出

```yaml
fib8: 21
```

## 文档

更多文档请访问 <https://kusionstack.io>

## 贡献

参考[开发手册](https://github.com/KusionStack/KCLVM/tree/main/docs/dev_guide).

## 路线规划

参考[KCLVM 路线规划](https://kusionstack.io/docs/governance/intro/roadmap#kclvm-%E8%B7%AF%E7%BA%BF%E8%A7%84%E5%88%92)

## 许可
Apache License Version 2.0