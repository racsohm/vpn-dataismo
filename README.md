# vpn-dataismo
Configuración de OpenVPN para dataismo

- Debes de colocar en el archivo key.pass los datos del usuario.
- En sistemas basados den debian puedes agregar en crontab: @reboot /dataismo/vpn/connect.sh > /dev/null 2>&1
- Para sistemas basados en fedora/Redhat/Oracle Linux requiere de la importación de la configuración: sudo openvpn3 config-acl --show --grant root --config VPN.
- a demás sobre el punto anterior:sudo openvpn3 config-acl --show --grant root --transfer-owner-owner-session true --config VPN
- Por último hacer que se inicie la conexión: sudo systemctl enable --now openvpn3-session@VPN.service.
- **NOTA:** Para freeNas(trueNas) se debe instalar por linea de comandos OpenVPN, para ellos debes de modificar el archivo de repositores de PKG ya que por defecto viene desactivado, y debes de desactivar los repositorios locales luego instalar OPENVPN, y nano para facilitar la edición de archivos