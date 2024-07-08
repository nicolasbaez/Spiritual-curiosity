# Spiritual-curiosity
How about a little apocalypse?

![buh](https://github.com/nicolasbaez/Spiritual-curiosity/blob/main/xp039.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = 0;
draw = (_) => {
  h = w / 2;
  clear();
  rotateX(1);
  rotateZ(0.1);
  s = sin(k / 3) * w * 0.2 + sin(k * 9);
  q = w / 18;
  for (i = -w; i < w; i += q)
    for (j = -w; j < w; j += q) {
      quad(
        i,
        j,
        noise(i, j, k) * s,
        i + q,
        j,
        noise(i + q, j, k) * s,
        i + q,
        j + q,
        noise(i + q, j + q, k) * s,
        i,
        j + q,
        noise(i, j + q, k) * s
      );
    }
  if (k == 0) saveGif("xp039.gif", 293, { delay: 0, units: "frames" });
  k += 0.1;
};
