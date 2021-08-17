# Learning Alpine.js

Just one of the things I'm learning. <https://github.com/hchiam/learning>

It feels like Bootstrap/Tailwind CSS utility classes in your HTML, but with JavaScript-in-HTML. 4KB! You can import/install `alpinejs`, or just use a CDN link! You could work entirely in your HTML file.

Live demo: <https://codepen.io/hchiam/pen/abWXXbX>

Fireship tutorial: <https://youtu.be/cuHDQhDhvPE?t=1115>

<https://alpinejs.dev>

<https://alpinejs.dev/start-here>

<https://github.com/alpinejs/alpine>

## Note: Alpine's convenient inline code breaks [CSP](https://github.com/hchiam/learning-csp)

<https://alpinejs.dev/advanced/csp>

```html
<!-- NOT CSP-safe due to inline JS: -->
<div x-data="{ count: 1 }">
  <button @click="count++">Increment</button>
  <span x-text="count"></span>
</div>
```

```html
<!-- This is more CSP-safe since inline JS is disabled: -->
<div x-data="counter">
  <button @click="increment">Increment</button>
  <span x-text="count"></span>
</div>
<script>
  // safer, but takes away from the appeal of simplicity versus other frameworks:
  Alpine.data("counter", () => ({
    count: 1,

    increment() {
      this.count++;
    },
  }));
</script>
```
