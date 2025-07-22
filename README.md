# vpn-dataismo
Configuración de OpenVPN para dataismo

- Debes de colocar en el archivo key.pass los datos del usuario.
- En sistemas basados den debian puedes agregar en crontab: @reboot /dataismo/vpn/connect.sh > /dev/null 2>&1
- Para sistemas basados en fedora/Redhat/Oracle Linux requiere de la importación de la configuración: sudo openvpn3 config-acl --show --grant root --config VPN.
- a demás sobre el punto anterior:sudo openvpn3 config-acl --show --grant root --transfer-owner-owner-session true --config VPN
- Por último hacer que se inicie la conexión: sudo systemctl enable --now openvpn3-session@VPN.service 