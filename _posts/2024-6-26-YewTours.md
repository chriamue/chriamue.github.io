---
layout: post
title: Yew Tours
---

Let me introduce you to my latest project: [Yew Tours](https://github.com/chriamue/yew-tou-rs)

Designed to enhance user onboarding experiences, Yew Tours is a library for creating interactive tours in applications built with the [Yew framework](https://yew.rs).

### Why Yew Tours?

When developing web applications, particularly those rich in features, it's essential to ensure users can navigate and understand the interface effortlessly. Yew Tours simplifies this process by offering a guided, step-by-step introduction to your application's features.

### Features

- **Step-by-Step Guidance**: Highlight key elements and provide detailed instructions for each step.
- **Easy Integration**: Seamlessly integrate with your existing Yew application.
- **Markdown Support**: Use markdown to format your tour content.

### Getting Started

Add Yew Tours to your `Cargo.toml`:

```toml
[dependencies]
yew = { version = "0.21.0", features = ["csr"] }
yew-tou-rs = { git = "https://github.com/chriamue/yew-tou-rs" }
```

Here’s a quick example of how to set up a tour:

```rust
use yew::prelude::*;
use yew_tou_rs::prelude::{Tour, TourStep};

#[function_component(App)]
pub fn app() -> Html {
    let steps = vec![
        TourStep {
            selector: ".h1-step".to_string(),
            content: "This is a title".to_string(),
        },
        TourStep {
            selector: ".p-step".to_string(),
            content: "This is a paragraph".to_string(),
        },
        TourStep {
            selector: ".button-step".to_string(),
            content: "This is a button".to_string(),
        },
        TourStep {
            selector: "footer".to_string(),
            content: "This is a footer".to_string(),
        }
    ];

    html! {
        <div class="app">
            <h1 class="h1-step">{"Hello, Yew Tou-rs"}</h1>
            <p class="p-step">{"This is a simple example of a Yew Tou-rs."}</p>
            <button class="button-step">{"Click me"}</button>
            <footer class="footer-step">
                <a href="https://github.com/chriamue/yew-tou-rs">{"yew-tou-rs"}</a>
            </footer>
            <Tour steps={steps} />
        </div>
    }
}

fn main() {
    yew::Renderer::<App>::new().render();
}
```

### Live Demo

Want to see Yew Tours in action? Check out the [live demo](https://chriamue.github.io/yew-tou-rs/demo/).

### Documentation

Documentation is available [here](https://chriamue.github.io/yew-tou-rs/doc/yew_tou_rs/). You'll find detailed information on how to customize your tours.

### Conclusion

Yew Tours aims to make it easier for you to create engaging onboarding experiences for your users. Your feedback is invaluable, so please try it out and let me know what you think.
