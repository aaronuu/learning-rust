---
date: 2019-03-26T07:00:00+08:00
title: 原始引用
menu:
  main:
    parent: "grammar-pointer"
weight: 362
description : "Rust中的原始引用"
---

Rust 支持两种原始引用：

- 不可变原始指针 `*const T`
- 可变原始指针 `*&mut T`

用 as 操作符可以将引用转为原始指针：

```rust
let mut x = 10;
let ptr_x = &mut x as *mut i32;
let y = Box::new(20);
let ptr_y = &*y as *const i32;

// 原生指针操作要放在unsafe中执行
unsafe {
    *ptr_x += *ptr_y;
}
assert_eq!(x, 30);
```




