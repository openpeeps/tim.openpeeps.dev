---
title: "Transpilation Overview"
description: "An overview of the source to source transpilation process in Tim Engine and the benefits it provides for developers using the engine."
keywords: ["transpilation", "overview", "tim engine", "template engine", "scripting language"]
---

## What's up with transpilation?
Transpilation is the process of converting source code from one programming language to another. In this case, Tim is capable of transpiling its own scripting language into multiple target languages, such as **JavaScript**, **Python**, **PHP**, **Lua**, **Ruby** and **Nim**. This allows developers to write their templates in Tim's scripting language while still being able to use the generated code in their preferred programming language.

<div class="alert alert-info rounded-4" role="alert">
  <div class="alert-content">
    The S2S transpilation process in Tim Engine is still in its early stages of development. The design and implementation of the transpiled code is subject to change as we continue to refine the process and gather feedback from developers.
  </div>
</div>

## Benefits of transpilation
Transpilation allows developers to write their templates in Tim's scripting language while still being able to use their favorite stack, tools and programming languages.

The front-end migration process can be a daunting task. Having your front-end logic written in scripting language like Tim can make the transition smoother, as you can transpile your existing code to the target language without having to rewrite it from scratch.

<div class="alert alert-info rounded-4" role="alert">
  <div class="alert-content">
    A pluggable transpilation engine is also in the works, which will allow developers to create custom transpilation targets and extend the capabilities of the transpilation process.
  </div>
</div>

### Transpiling to JavaScript
Transpiling a Tim template to JavaScript is straightforward. Here, we have a simple Tim template that includes a variable and some HTML elements:
```
// Tim template with scripting language
div.container
  var name = "Tim Engine"
  p: $name
```

Now, using the `src` command, we can pass `--ext:js` to specify the target language for transpilation:
```text
tim src example.timl --ext:js
```

The resulting JavaScript code would look something like this:
```js
class Test {
  static render() {
    let html = "";
    {
      html += `<div class=\"container\">`;
        /** @type {any} */
        let name = "Tim Engine";
        {
          html += `<p>`;
          html += String(name);
          html += `</p>`;
        }
      html += `</div>`;
    }
    return html;
  }
}
module.exports = Test;
```

As you can see from the example, the Tim template is transpiled into a JavaScript class with a static `render` method that generates the HTML output. The variable `name` is defined and used within the method, demonstrating how the scripting language is transpiled into JavaScript code.

### Transpiling to Ruby
Transpiling the same template into Ruby is also possible using the `--ext:rb` flag. This will generate the following Ruby code:
```ruby
class Test
  # @param args [Array] Additional arguments (not used in this method).
  # @return [String] The generated HTML for the homepage.
  def self.render(*args)
    html = +""
    html << "<div class=\"container\">"
        name = "Tim Engine"
        html << "<p>"
        html << name
        html << "</p>"
    html << "</div>"
    html
  end
end
```