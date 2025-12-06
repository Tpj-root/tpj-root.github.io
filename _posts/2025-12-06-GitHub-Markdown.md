---
layout: post
title: "GitHub Markdown Editing — Basic to Master"
categories: blog
published: false
---

---

# ✅ **GitHub Markdown Editing — Basic to Master**

## **1. BASIC (Beginner)**

### ✔ How to edit a `.md` file on GitHub

1. Open your repository
2. Click the file (example: `README.md`)
3. Click **Edit (pencil icon)**
4. Make changes
5. Scroll down → add commit message
6. Click **Commit changes**

Done.

### ✔ Basic Markdown formatting

```
# Heading 1
## Heading 2
### Heading 3

**bold**  
*italic*  
~~strike~~

- list item
- list item

1. number list
2. next
```

---

# ✅ **2. INTERMEDIATE (Useful Daily Skills)**

### ✔ Links

```
[Google](https://google.com)

[About Me](about.html)
```

### ✔ Images

```
![alt text](/assets/image/myphoto.png)
```

### ✔ Code Blocks

````markdown
```python
print("Hello")
```
````

### ✔ Inline Code

```
Use `ls` to list files.
```

### ✔ Blockquotes

```
> This is a quote.
```

### ✔ Horizontal Line

```
---
```

---

# ✅ **3. ADVANCED (For GitHub Pages / Projects)**

### ✔ Front Matter (Jekyll)

Used in posts & pages:

```
---
layout: post
title: My First Post
categories: blog
---
```

### ✔ Internal Links

```
[Projects](/projects/)
[Blog](/blog/)
[About](/about.html)
```

### ✔ Adding images to your site

1. Place images in:
   `/assets/image/your-file.png`
2. Use in Markdown:

   ```
   ![](/assets/image/your-file.png)
   ```

### ✔ Table

```
| Name | Age |
|------|-----|
| Sab  | 25  |
```

### ✔ Highlight / Note

```
**Note:** This is important.
```

---

# ✅ **4. MASTER LEVEL (Full Control)**

### ✔ Create new pages

Create a file like:

`projects/index.md`

```
---
layout: page
title: Projects
permalink: /projects/
---

# My Projects
```

### ✔ Create blog posts

Inside `_posts/`:

`2025-02-20-My-Post.md`

```
---
layout: post
title: My CNC Tool
categories: projects
---
```

### ✔ Use categories

```
categories: blog
categories: projects
categories: WhatAppChannel
```

### ✔ Loop posts (list specific category)

```
{% for post in site.posts %}
  {% if post.categories contains "blog" %}
  - [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}
```

### ✔ Add navigation

Edit `_data/navigation.yml`:

```
- title: Home
  url: /
- title: Blog
  url: /blog/
- title: Projects
  url: /projects/
```

### ✔ Hide a file from showing

Add:

```
published: false
```

---



In Jekyll (and GitHub Pages), **post filenames must follow a special format**:

```
YYYY-MM-DD-title.md
```

### Why:

1. **Date is important**

   * `YYYY-MM-DD` tells Jekyll the **post date** automatically.
   * Used for sorting posts (latest first) and generating URLs.

2. **Unique identifier**

   * The combination of date + title ensures no two posts clash.

3. **Automatic permalink**

   * Example: `_posts/1992-02-20-Hello.md` → URL:

     ```
     /1992/02/20/hello.html
     ```

     (unless you customize permalinks in `_config.yml`)

4. **Works with Jekyll loops**

   * `site.posts` automatically reads `_posts/` files using this format.

---

### Example:

```md
# _posts/2025-12-06-My-CNC-Tool.md
---
layout: post
title: "My CNC Tool"
categories: projects
---
```

* Date → `2025-12-06`
* Title → `My CNC Tool`
* Jekyll sorts it correctly and generates links automatically.

---

**Tip:**
If you want drafts without a date, put them in `_drafts/` folder. Then you can publish later by moving them to `_posts/` with the correct `YYYY-MM-DD-title.md` format.





```yaml
---
layout: page
title: WhatAppChannel
permalink: /WhatAppChannel/
---

# WhatsApp Channel

{% for post in site.posts %}
  {% if post.categories contains "WhatAppChannel" and post.published != false %}
  - **[{{ post.title }}]({{ post.url }})**  
    <small>{{ post.date | date: "%b %d, %Y" }}</small>
  {% endif %}
{% endfor %}
```

### ✅ How it works:

1. In any post, add:

```yaml
published: false
```

2. That post **will NOT appear** on the `WhatAppChannel` page (or any loop checking for `post.published != false`), but the file still exists in `_posts`.

This is useful for **drafts** or posts you want to keep but not show publicly.




* If you **don’t set `published`**, Jekyll treats it as `true`.
* Setting `published: true` explicitly doesn’t change anything — the post will appear normally.

**Example:**

```yaml
---
layout: post
title: "My Visible Post"
categories: WhatAppChannel
published: true
---
```

This post will appear in loops like:

```liquid
{% for post in site.posts %}
  {% if post.categories contains "WhatAppChannel" and post.published != false %}
  - [{{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}
```

✅ It will show exactly like a normal post.

Use `published: false` only when you want to **hide the post temporarily**.


