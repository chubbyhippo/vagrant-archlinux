Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"
    config.vm.synced_folder ".", "/home/vagrant/dev"
    config.vm.network "forwarded_port", guest: 3000, host: 3000
    config.vm.provision "shell", reboot: true, inline: <<-SHELL
        sudo pacman -Syu --noconfirm
        sudo pacman -S --noconfirm docker docker-compose
        sudo usermod -aG docker vagrant
        sudo systemctl enable docker.service
    SHELL
end