**#1. Khái quát KVM** 
-	KVM là giải pháp ảo hóa cho hệ thống linux trên nền tảng phần cứng x86
-	Chính xác thì KVM là một module của kernel linux hỗ trợ cơ chế mapping các chỉ dẫn xuất phát từ cpu ảo lên cpu thật
-	Thường thì các hypervisor khác (type 2) thường sử dụng các translator để thực hiệc cơ chế mapping này. Tuy nhiên hiệu suất không thực sự cao
-	KMV thường đi liền với QEMU là 1 hypervisor loại 2, KVM đống vai trò như Accelerator thay vì sử dụng các translator khác, cho hiệu suất cao hơn
-	Tính cô lập trong sử dụng KVM: các VM hoạt động như các process trên nền linux nên tận dụng được các tính năng bảo mật của linux để cô lập tài nguyên cũng như hoạt động của các VM. Thường thì SVirt sẽ đảm bảo tài nguyên của các máy ảo không thể bị truy cập bởi bất kì tiến trình nào khác.
-	KVM hỗ trợ live migration các VM giữa các host vật lý, đứng từ người dùng thì quá trình này là trong suốt. KVM cũng hỗ trợ snapshot các máy ảo
**thangnd**