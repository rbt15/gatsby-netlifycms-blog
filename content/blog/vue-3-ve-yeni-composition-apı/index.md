---
title: Vue 3 ve yeni Composition API
date: 2020-09-26T10:43:13.910Z
description: Deneme Post
---
```csharp
[HttpPost]
public async Task<IActionResult> Create(PostViewModel vm)
{
    var post = new Post
    {
        PostId = vm.PostId,
        PostTitle = vm.PostTitle,
        PostBody = vm.PostBody,
        Image = await _fileManager.SaveImage(vm.Image)
    };
    if (post.PostId > 0)
        _repo.UpdatePost(post);
    else
        _repo.AddPost(post);


    if (await _repo.SaveChangesAsync())
        return RedirectToAction( "Post", new RouteValueDictionary( 
            new {  action = "Post", Id = post.PostId } ) );
    return View(vm);
}
```

## .net core controller

![duo tone](duotone.png "splash")

> Lorem ipsumasd
>
> `console.log()`

``

arthur