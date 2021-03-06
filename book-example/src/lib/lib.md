# Rust Library

mdBook is not only a command line tool, it can be used as a crate. You can extend it,
integrate it in current projects. Here is a short example:

```rust,ignore
extern crate mdbook;

use mdbook::MDBook;
use std::path::Path;

# #[allow(unused_variables)]
fn main() {
    let mut book =  MDBook::new("my-book")        // Path to root
                        .with_source("src")       // Path from root to source directory
                        .with_destination("book") // Path from root to output directory
                        .read_config()            // Parse book.toml or book.json configuration file
                        .expect("I don't handle configuration file error, but you should!");

    book.build().unwrap();                        // Render the book
}
```

Check here for the [API docs](mdbook/index.html) generated by rustdoc.
