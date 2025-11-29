Este é um projeto básico e simplificado para cumprir o desafio de auditoria usando Kali Linux, Medusa e a VM vulnerável Metasploitable 2.

O objetivo é mostrar um único ataque de força bruta (FTP), com passos claros e curtos para facilitar.

1) Ambiente utilizado

Kali Linux (atacante)

Metasploitable 2 (alvo)

Rede: Host-Only no VirtualBox (as máquinas se enxergam, mas ficam isoladas).

IP usado no exemplo do Metasploitable: 192.168.56.102 (pode variar ).
3) Teste de força bruta usando Medusa (FTP)

O Metasploitable 2 vem com o serviço FTP vulnerável habilitado.

Comando utilizado
medusa -h 192.168.56.102 -U wordlists/users.txt -P wordlists/passwords.txt -M ftp
Explicação:

-h: IP do alvo

-U: arquivo com usuários

-P: arquivo com senhas

-M ftp: módulo FTP do Medusa

Quando o Medusa encontrar uma credencial válida, ele vai mostrar algo como:

ACCOUNT FOUND: [ftp] [ftp] Host: 192.168.56.102
4) Validação do acesso

Após encontrar um login válido, teste manualmente:

ftp 192.168.56.102

Digite o usuário e senha encontrados pelo Medusa.

Se conseguir acessar, significa que a força bruta foi bem-sucedida.

5) Medidas básicas de mitigação

Usar senhas mais fortes.

Bloqueio automático após várias tentativas de login.

Desativar o FTP ou usar alternativas mais seguras (SFTP/SSH).

Monitorar logs de tentativas de autenticação.

