# Code thêm email mới vào tài khoản Facebook không checkpoint

Việc thêm một địa chỉ email mới và lạ vào tài khoản Facebook rất dễ dẫn đến tình trạng bị checkpoint (khoá bảo mật). Vậy làm cách nào để thực hiện việc này một cách an toàn nhất? Cùng theo dõi bài viết này nhé!

## Các bước thực hiện

**Bước 1:** Truy cập https://www.facebook.com/settings/?tab=account <br>
**Bước 2:** Bấm chuột phải vào màn hình → chọn **Kiểm tra** <br>
**Bước 3:** Cửa sổ **DevTools** được bật lên → chon tab **Console** → Màn hình hiển thị cảnh báo **Dừng lại** <br>
**Bước 4:** Copy toàn bộ code dưới đây:<br>

``` .js
var spinR = require(["SiteData"]).__spin_r;
var spinB = require(["SiteData"]).__spin_b;
var spinT = require(["SiteData"]).__spin_t;
var jazoest = require(["SprinkleConfig"]).jazoest;
var fbdtsg = require(["DTSGInitData"]).token;
var userId = require(["CurrentUserInitialData"]).USER_ID;
var hsi = require(["SiteData"]).hsi;
var email = "<span class="block">taikhoancuaban@gmail.com</span>";
var url = "https://www.facebook.com/add_contactpoint/dialog/submit/";
var data = "jazoest=22134&amp;fb_dtsg=" + fbdtsg + "&amp;next=&amp;contactpoint=" + email + "&amp;__user=" + userId + "&amp;__a=1&amp;__dyn=&amp;__req=1&amp;__be=1&amp;__pc=PHASED%3ADEFAULT&amp;dpr=1&amp;__rev=&amp;__s=&amp;__hsi=" + hsi + "&amp;__spin_r=" + spinR + "&amp;__spin_b=" + spinB + "&amp;__spin_t=" + spinT;
fetch(url, {
	method: 'POST',
	body: data,
	headers: {
		'Content-Type': 'application/x-www-form-urlencoded'
	}
}).then(e =&gt; e.text()).then(e =&gt; {})
```

- Thay `taikhoancuaban@gmail.com`  thành thành email của bạn!
