# Tìm hiểu KVM (Kernel-Base Virtual Machine)
# Mục lục
<h3><a href="#khainiem">1. Khái niệm</a></h3>
<h3><a href="#kvmstack">2. KVM Stack</a></h3>
<h3><a href="#qemu">3. KVM - QEMU<a/></h3>
<h3><a href="#tinhnang"4>. Tính năng KVM</a></h3>
<ul>
<li><a href="#secu">4.1. Security</a></li>
<li><a href="#memmgr">4.2. Memory Management</a></li>
<li><a href="#storage">4.3. Storage</a></li>
<li><a href="#migrate">4.4. Live migration</a></li>
<li><a href="#performance">4.5. Performance and scalability</a></li>
</ul>
<h3><a href="#ref">5. Tham khảo</a></h3>

---------------------------------------

<h2><a name="khainiem">1. Khái niệm</a></h2>
<div>
KVM là giải pháp ảo hóa cho hệ thống linux trên nền tảng x86 có các module hỗ trợ ảo hóa (Intel VT-x hoặc AMD-V.
<br>
Về bản chất thì KVM không hẳn là một hypervisor giả lập phần cứng hệ thống, chính xác hơn thì KVM là một module trong kernel Linux hỗ trợ mapping các chỉ dẫn trên vCPU lên CPU vật lý.
</div>
<h2><a name="kvmstack">2.KVM Stack</a></h2>
<div>
<img src="http://i.imgur.com/dUhDP88.png"/>
<b>KVM Stack gồm 4 phần:</b>
<ul>
<li><b>User-facing tools</b>: là các công cụ quản lý máy ảo hỗ trợ KVM như virt-manager hoặc giao diện dòng lệnh như virsh.</li>
<li><b>Managerment layer:</b> Lớp này là thư viện libvirt cung cấp API để các công cụ quản lý máy ảo hoặc các hypervisor tương tác với KVM thực hiện các thao tác quản lý tài nguyên ảo hóa, vì tự thân KVM không hề có khả năng giả lập và quản lý tài nguyên như vậy.</li>
<li><b>Virtual Machine:</b> Chính là các máy ảo người dùng tạo ra. Thông thường, nếu không sử dụng các công cụ như virsh hay <b>virt-manager</b>, <b>KVM</b> sẽ sử được sử dụng phối hợp với một hypervisor khác điển hình là <a href="#qemu"><b>QEMU</b></a>.</li>
<li><b>Kernel support:</b>Chính là KVM, cung cấp một module làm hạt nhân cho hạ tầng ảo hóa (kvm.ko) và một module kernel đặc biệt hỗ trợ các vi xử lý VT-x hoặc AMD-V (kvm-intel.ko hoặc kvm-amd.ko)</li>
</ul>
</div>
<h2><a name="qemu">3. KVM - QEMU</a></h2>
<div>
KVM thường đi liền với QEMU. Về cơ bản, QEMU là một hypervisor hoàn chỉnh (type 2) có thể mô phỏng phần cứng, thông thường các hypervisor sử dụng 1 <b>translator</b> để mapping các chỉ dẫn từ vCPU đến CPU vật lý (gọi là <b>TCG - Tyny Core Generator</b>) tuy nhiên hiệu suất thường không cao. Tận dụng tính năng của KVM, KVm đóng vai trò như 1 <b>accelerator</b> (thay thế cho TCG).
</div>
<h2><b><a name="tinhnang">4. Tính năng</a></b></h2>
<ul>
<li><h2><b><a name="secu">4.1 Security</a></b></h2>
<div>

<br>

</div>
</li>
<li><h2><b><a name="memmgr">4.2 memory managerent</a></b></h2>
<div>

<br>

</div>
</li>
<li><h2><b><a name="storage"> 4.3 Storage</a></b></h2>
<div>

<br>

</div
</li>
<li><h2><b><a name="migrate">4.4 Migrate</a></b></h2>
<div>

<br>

</div>
</li>
<li><h2><b><a name="performance">4.5 Performance and scalability</a></b></h2>
<div>

<br>

</div>
</li>
</ul>
