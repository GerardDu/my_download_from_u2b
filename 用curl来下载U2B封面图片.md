# 用curl来下载U2B封面图片

//2026年11月26日

```
我使用：

视频链接：
https://www.youtube.com/watch?v=4e1bkPeMWX8

下载封面链接：（保存到当前终端的工作目录下，文件名为cover.jpg）
curl -fL "https://img.youtube.com/vi/4e1bkPeMWX8/maxresdefault.jpg" -o "cover.jpg"
```

使用时，只要修改视频链接即可。

## 1.下载命令

在 Windows 10 PowerShell 中，可以直接使用 `curl` 下载 YouTube 视频封面。

### **1. 下载最高分辨率封面**

```
curl.exe -L "https://img.youtube.com/vi/KrVH-MKJviI/maxresdefault.jpg" -o "cover.jpg"
```

参数说明：

- `curl.exe`：调用 Windows 中的 curl 程序。
- `-L`：自动跟随 HTTP 重定向。
- `-o`：指定下载后的文件名。
- `maxresdefault.jpg`：请求最高分辨率封面（通常为 1280×720）。

### **2. 其他分辨率**

只需要替换 URL 最后的文件名：

| 文件名              | 分辨率   |
| ------------------- | -------- |
| `maxresdefault.jpg` | 1280×720 |
| `sddefault.jpg`     | 640×480  |
| `hqdefault.jpg`     | 480×360  |
| `mqdefault.jpg`     | 320×180  |
| `default.jpg`       | 120×90   |

### **3. 指定保存目录**

例如保存到 `D:\YouTube\Thumbnails`：

```
curl.exe -L "https://img.youtube.com/vi/KrVH-MKJviI/maxresdefault.jpg" -o "D:\YouTube\Thumbnails\KrVH-MKJviI.jpg"
```

注意：请确保目标目录已经存在。

### **4. 下载前检查 HTTP 状态码**

```
curl.exe -L -I "https://img.youtube.com/vi/KrVH-MKJviI/maxresdefault.jpg"
```

如果返回：

```
HTTP/1.1 200 OK
```

通常说明图片资源存在。

**推荐你以后直接使用这一条命令：**

```
curl.exe -fL "https://img.youtube.com/vi/视频ID/maxresdefault.jpg" -o "cover.jpg"
```

增加 `-f` 后，遇到 HTTP 404 等错误状态时，curl 会返回失败，而不是把错误页面保存成图片。

## 2.



## 3.



