# Monitoração e Automação
Subindo ambientes de monitoração e automação com Docker.
#Zabbix
Zabbix é uma ferramenta de monitoração open source, essencial para medir o desempenho e disponibilidade da infraestrutura e serviços.
Nesse exemplo, vamos construir um ambiente de monitoração com o Zabbix, em poucos segundos, através do Docker-Compose.
A arquitetura do Zabbix será distribuída, ou seja, cada componente (Zabbix-Frontend, Zabbix-Server, Zabbix-Database, Zabbix-Proxy, Zabbix-Java-Gateway e Zabbix-Agent) será executado em container. . Siga os passos a seguir:
- 1 - Faça o pull desse repositório na sua máquina local
- 2 - Dentro do diretório, execute o seguinte comando para criar e inicializar os containers em background: docker-compose -f docker-compose-zabbix.yml up -d
- 3 - Verifique se todos os serviços estão UP: docker-compose -f docker-compose-zabbix.yml ps
- 4 - Abra a seguinte URL no seu browser, para ter acesso ao console do Zabbix: http://localhost:8888/zabbix
- 5 - Faça o login com o usuário e senha padrão: . Usuário: Admin . Senha: zabbix
- OBS: Na primeira execução do docker-compose, deve demorar ao carregar a tela de login, pois a base de dados do Zabbix estará sendo populada. Depois, o processo vai ser mais rápido, pois será carregado os dados armazenados no volume da máquina local.
- 6 - Caso queira parar todos os serviços, execute o seguinte comando: docker-compose -f docker-compose-zabbix.yml stop
- 7 - Caso queira parar e remover todos os serviços, execute o seguinte comando: docker-compose -f docker-compose-zabbix.yml down
- 8 - Caso queira modificar algum parâmetro de determinado(s) serviço(s) no arquivo .yml, para que o docker-compose entenda a modificação e você não precise parar/remover todos os serviços, execute os seguintes comandos:
- Parando o serviço: docker-compose -f docker-compose-zabbix.yml stop nome_do_servico
- Removendo o serviço: docker-compose -f docker-compose-zabbix.yml rm nome_do_servico
- Criando/Recriando o serviço: docker-compose -f docker-compose-zabbix.yml create nome_do_servico
- Inicializando o serviço: docker-compose -f docker-compose-zabbix.yml start nome_do_servico
# Em breve darei continuidade com o laboratório com o Zabbix, e publicarei novas tecnologias e ambientes de monitoração e automação, utilizando o Docker-Compose
