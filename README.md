Descrição do Projeto
Parte 1 — Serviço systemd para inicialização automática

O objetivo desta etapa foi configurar um serviço utilizando systemd para executar automaticamente um programa de controle de GPIO durante o processo de inicialização da Raspberry Pi.

Primeiro, foi desenvolvido um script em Bash responsável por controlar um LED conectado a um pino GPIO. O script utilizou a interface exposta em /sys/class/gpio/ para exportar o pino, definir sua direção e alternar o valor lógico entre alto e baixo, permitindo o acionamento periódico do LED. Após a validação da execução manual do script, criou-se um arquivo de unidade do systemd (blink.service) especificando o caminho do script em ExecStart e definindo o alvo de inicialização por meio de WantedBy.

O arquivo de unidade foi copiado para o diretório padrão do systemd e testado com o utilitário systemctl. Em seguida, o serviço foi habilitado para iniciar automaticamente no boot por meio do comando systemctl enable, permitindo que o script fosse executado logo no processo de inicialização do sistema operacional.

Parte 2 — Controle de versão com Git e integração com GitHub

Nesta etapa, o projeto foi versionado utilizando Git diretamente na Raspberry Pi. O repositório local foi inicializado, configurado e teve seus arquivos adicionados e versionados ao longo do desenvolvimento.

Após isso, foi criado um repositório remoto no GitHub, e a autenticação foi configurada por meio de um token pessoal de acesso. O repositório local foi conectado ao remoto e as versões produzidas foram enviadas utilizando git push. O histórico de alterações foi registrado com o comando git log, conforme solicitado na prática.

Montagem utilizada

A montagem consistiu na conexão de um LED e resistor à protoboard, ligados ao pino GPIO utilizado no script, conforme a imagem abaixo:
