                                                    Laboratório — Sessão 3

Hardening de Redes Linux e Configuração de Firewalls

Objetivo: Configurar uma política defensiva estrita para impedir acessos não autorizados a serviços críticos do servidor, combinando UFW e iptables.


         Tarefas
    1. Foi executado o comando "sudo ufw status" para verificar o estado atual do UFW
<img width="316" height="208" alt="image" src="https://github.com/user-attachments/assets/51c1c558-6950-454b-b965-40e1588185d5" />

    2. Foi executado o comando "sudo ufw default deny incoming" para bloquear as ligações de entrada e o comando "sudo ufw default allow outgoing" para permitir as ligações de saída.
  <img width="327" height="196" alt="image" src="https://github.com/user-attachments/assets/5394ed56-e813-4fef-abd2-a2e7286c70e2" />
   
  <img width="535" height="203" alt="image" src="https://github.com/user-attachments/assets/f07b3236-6a5c-4929-ad31-691e9a5b2fb8" />

    3. Foi executado o comando "sudo ufw allow 22/tcp" para criar uma regra específica para permitir acesso SSH apenas na porta padrão
<img width="547" height="260" alt="image" src="https://github.com/user-attachments/assets/f31a51cc-fcb6-4fc9-a0df-9bb0bf49cf2b" />

    4. Foi executado o comando "udo iptables -A INPUT -s 203.0.113.50 -j DROP" para simular o bloqueio de um IP malicioso fictício na chain INPUT do iptables
<img width="539" height="275" alt="image" src="https://github.com/user-attachments/assets/ec3e5def-5023-447a-8def-29438e116bd0" />

    5. Foi executado o camando "sudo iptables-save | sudo tee /etc/iptables/rules.v4" para guardar o estado persistente do iptables

<img width="551" height="427" alt="image" src="https://github.com/user-attachments/assets/a2518143-59c8-4393-b257-b9ec6e087e93" />


Foi definida a política padrão do UFW para bloquear todas as ligações de entrada (deny incoming) e permitir todas as ligações de saída (allow outgoing). Também foi criada uma regra para permitir ligações SSH através da porta TCP 22.

No iptables foi adicionada uma regra para bloquear o endereço IP fictício 203.0.113.50, simulando o bloqueio de um endereço considerado malicioso.

