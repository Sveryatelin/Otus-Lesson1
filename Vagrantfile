MACHINES = {
# Указываем имя ВМ для vagrant
:"ubuntu22-lesson1" => {
            #Какой vm box будем использовать
            :box_name => "ubuntu/jammy64",
            #Указываем количество ядер ВМ
            :cpus => 2,
            #Указываем количество ОЗУ в мегабайтах
            :memory => 2048,
            #Имя ВМ для virtual box
            :vm_name => "ubuntu22-lesson1"
          }
}

Vagrant.configure("2") do |config|
MACHINES.each do |boxname, boxconfig|
  # Отключаем проброс общей папки в ВМ
  config.vm.synced_folder ".", "/vagrant", disabled: true
  # Получение IP адреса по dhcp
  config.vm.network "public_network"
  # Применяем конфигурацию ВМ
  config.vm.define boxname do |box|
    box.vm.box = boxconfig[:box_name]
    box.vm.host_name = boxconfig[:vm_name]
    box.vm.provider "virtualbox" do |v|
      v.memory = boxconfig[:memory]
      v.cpus = boxconfig[:cpus]

    end
  end
  
end
end 