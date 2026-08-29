# MovieStream remote configuration

`tmdb_hosts.json` controls the preferred TMDb API domains used by the patched
Umbrella, Homelander, and POV Kodi add-ons.

Put the preferred domain first. Keep at least one known-good fallback domain.
The add-ons validate the file, refresh it every 15 minutes, cache the last valid
copy, and retain built-in fallback domains if GitHub is temporarily unavailable.

Current configuration example:

```json
{
  "version": 1,
  "tmdb_api_hosts": [
    "api.tmdb.org",
    "api.themoviedb.org"
  ]
}
```

Only bare DNS hostnames are accepted: do not include `https://`, paths, ports,
or query strings.

## Cách đổi miền sau này

Sửa mảng `tmdb_api_hosts`, đặt miền ưu tiên ở dòng đầu rồi commit vào nhánh
`main`. Ba add-on sẽ tự kiểm tra lại trong tối đa 15 phút; không cần sửa hoặc
cài lại plugin. Nếu GitHub tạm thời không truy cập được, add-on tiếp tục dùng
bản hợp lệ gần nhất đã lưu trên Kodi.

## Bảo mật

Chỉ thêm miền TMDb/proxy do bạn tin cậy. Các miền trong danh sách sẽ nhận yêu
cầu TMDb, có thể gồm API key hoặc access token. Nên bật xác thực hai lớp cho tài
khoản GitHub và không cấp quyền ghi repo cho người lạ.
