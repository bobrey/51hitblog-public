һ��
��C�̸�Ŀ¼�½���menu.lst�ļ����ü��±��༭������������ճ����ȥ�󣬱����˳�
color blue/green yellow/red white/magenta white/magenta
timeout 30
default /default

title CentOS
kernel (hd0,0)/isolinux/vmlinuz
initrd (hd0,0)/isolinux/initrd.img

PS����hd0,0���������ݵ������������ͬ
/"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""/
���������£�����diskpart
list disk
select disk 0
list partition
select partition 8
detail partition
ȷ��c�����ڷ���

//________________________________________________________________________________________//
�Թ���ԱȨ�޴������
bcdedit /create /d "grub" /application bootsector
  ��ʾ����һ��{id}
  example:{6ad1ccb4-9b6b-11df-84a0-da2f4806d80e}

  bcdedit /set {6ad1ccb4-9b6b-11df-84a0-da2f4806d80e} device partition=C:
  bcdedit /set {6ad1ccb4-9b6b-11df-84a0-da2f4806d80e} path \grldr.mbr
  bcdedit /displayorder {6ad1ccb4-9b6b-11df-84a0-da2f4806d80e} /addlast


������������ʱ��������������grubѡ�ע�⣺��Winϵͳ�У�����������ԣ��߼�ϵͳ���ã��߼��������͹��ϻָ���Ҫ��ѡ"��ʾ����ϵͳ�б��ʱ��"��ѡ��grub�������CentOS,�س���ʼ��װ����װ�̳������У���Ҫע���������directory holding images��__ʱ��Ҫѡ��CentOS ISO�ļ����ڷ�����

�����Ӻ����˫ϵͳ��װ���