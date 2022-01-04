# Show And Complete A To-Do Item

You're almost done with testing this application! Have a look at the method that
completes a to-do item.

```javascript
else if (req.url.startsWith('/items/') && req.method === 'POST') {
  const index = Number.parseInt(req.url.substring(7)) - 1;
  items[index].isComplete = true;
  res.setHeader('Location', '/items');
  res.writeHead(302);
}
```

That's interesting. There's nothing to test there, no methods. That's some kind
of wonderful! On to the next item!
