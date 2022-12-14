# 目录

[序言](preface.md)

- [简介](intro/readme.md)
- [标准库](stdlib/readme.md)
  - [排序算法: Timsort 和 pdqsort](stdlib/sort/readme.md)
- [Rust编译器](rustc/readme.md)
  - [概述](rustc/overview/readme.md)
  - [命令行解析](rustc/invocation/readme.md)
  - [词法分析](rustc/lexer/readme.md)
  - [语法分析](rustc/parser/readme.md)
    <!-- - [抽象语法树](rustc/parser/ast/readme.md)
      - [抽象语法树定义](rustc/parser/ast/ast.md)
      - [访问者模式](rustc/parser/ast/visitor.md)
    - [EarlyLint](rustc/parser/early-lint/readme.md) -->
  - [语义分析](rustc/sema/readme.md)
    - [Lint](rustc/sema/lint/readme.md)
      <!-- - [Lint 与 LintPass](rustc/sema/lint/lint-pass.md)
      - [CombinedLintPass](rustc/sema/lint/combinedlintpass.md)
      - [Lint 执行流程[WIP]](rustc/sema/lint/lint.md) -->
    <!-- - [Resolver](rustc/sema/resovler/readme.md)
    - [HIR lowering](rustc/sema/hir-lowering/readme.md)
      - [类型推导](rustc/sema/hir-lowering/type-inference/readme.md)
      - [Trait solving](rustc/sema/hir-lowering/trait-solving/readme.md)
      - [类型检查](rustc/sema/hir-lowering/type-checking/readme.md)
      - [LateLint](rustc/sema/late-lint/readme.md)
    - [MIR lowering](rustc/sema/mir-lowering/readme.md)
      - [Borrow checking](rustc/sema/mir-lowering/borrow-check/readme.md)
      - [MIR 优化](rustc/sema/mir-lowering/mir-optimized/readme.md) -->
  - [代码生成](rustc/codegen/readme.md)
  - [通用结构](rustc/general/readme.md)
    - [Rust 错误信息输出原理概述](rustc/general/errors/readme.md)
    - [SourceMap & Span[WIP]](rustc/general/sourcemap-span/readme.md)

- [Rust外围工具](rust-tools/readme.md)
  <!-- - [Cargo包管理](rust-tools/cargo/readme.md)
  - [Clippy](rust-tools/clippy/readme.md) -->

- [Rust开源项目](open-source/readme.md)
  - [KCLVM](open-source/KCLVM/readme.md)

- [附录](appendix/readme.md)
