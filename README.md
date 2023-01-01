## getHexColorFromColorName

```
const getHexColorFromColorName = (colorName) => {
  let element = document.createElement("div");
  element.style.color = colorName;
  element.style.display = "none";
  document.body.appendChild(element);
  let rgbColor = window.getComputedStyle(element).color,
    rgbStr = rgbColor.replace(/([rgbaRGBA() ])/g, ""),
    hexColor =
      "#" +
      (
        (1 << 24) +
        ((Number(rgbStr.split(",")?.[0]) || 0) << 16) +
        ((Number(rgbStr.split(",")?.[1]) || 0) << 8) +
        (Number(rgbStr.split(",")?.[2]) || 0)
      )
        .toString(16)
        .slice(1);
  return hexColor;
};
```
