# __Integra-o-Proxmox-ao-google-drive__

### __1- Acesso à interface de linha de comando.__

O primeiro passo é acessar o PVE(Proxmox web).
	Em seguida, clicar no node da máquina.
  ![Tela inicial PVE; Localizando o Node](img/img1.png)

Ao clicar no node, algumas opções aparecerão no canto superior direito da tela. Clique em “Shell”.
	![Abrindo terminal do node escolhido](img/img2.png)

### __1.1 - Instalação e configuração do serviço rclone.__

O rclone é responsável por tornar a comunicação possível.Quando clicar, um terminal será aberto. Nesse terminal teremos que realizar a instalação e configuração do Rclone. Para instala-lo, basta apenas um comando simples, mas sua configuração precisa ser seguida com cuidado e atenção. Siga os comandos abaixo(Todos os comandos serão acompanhados pela sua devida explicação na linha subsequente a ele. Nenhum comando será maior que uma linha):


__apt install rclone -y__
Comando para instalar o rclone.

### __1.1.2 - Configuração rclone.__

O rclone funciona obedecendo um arquivo de configuração que é criado no momento da instalação, mas que vem vazio. Para ajustar ele, vamos configura-lo.

__rclone config__
Comando para abrir o painel de configuração do serviço.<br>
![Tela de configuração do rclone](img/img3.png) <br>

Quando o comando for digitado, algumas opções aparecerão. Vamos digitar __n__ para selecionar “New remote”. Após selecionar, serão exibidas varias configurações. Basta seguir os passos abaixo.<br>

__Nome:__ gdrive (Pressione Enter)<br>
__Storage:__ Procure o número correspondente ao Google Drive e digite ele, em seguida pressione Enter.<br>
__Client ID:__ Deixar em branco (pressione Enter).<br>
__Client secret:__ Deixar em branco (pressione Enter).<br>
__Scope:__ Escolha a opção 1 (Full access)e em seguida pressione Enter.<br>
__Service Account File:__ Deixe em branco (pressione Enter).<br>
__Edit advanced config:__ n (Pressione Enter).<br>
__Use auto-config:__ n (Pressione Enter)<br>

O sistema agora deve pedir um token. Esse token é exclusivo de cada ligação com cada conta. Para conseguir o token, siga o passo a passo abaixo com muita atenção!<br>

1.1.3 - Obtenção do token.<br>
	1.1.3.2 - Necessário apenas na primeira vez que for executar o procedimento no seu próprio computador.<br>

No seu computador agora, acesse: [https://rclone.org/downloads/](https://rclone.org/downloads/) <br>
Desça a tela um pouco até aparecer uma tabela com opções de download. Se estiver no Windows, basta clicar na opção destacada na imagem abaixo. Senão, selecione de acordo com seu sistema operacional. <br>

![Opção de Download do rclone para sistema Windows](img/img4.png) <br>

Após baixar, o arquivo virá compactado. <br>
![Pasta compactada baixada](img/img5.png)<br>

Clique com o botão direito no arquivo e clique em “Extrair tudo”.<br>
![Extrair pasta](img/img6.png) <br>

Uma nova janela será aberta. Clique em “Extrair”.
![Escolher local de destino para a extração](img/img7.png)<br>

Após o fim da extração, será gerada uma pasta. Renoimeie-a para “rclone”.<br>

Clique uma vez em cima da pasta e pressione “CTRL + X” para recortar a pasta. Agora, no menu lateral esquerdo o explorador de arquivos, desça até achar “Disco local (C:)” e clicar nele. Pressione “CTRL + V” para colar a pasta ali.<br>

Abra a pasta e clique no endereço dela e pressione “CTRL+C” para copiar o endereço.<br>




Dê 2 cliques no arquivo rclone.exe para baixar-lo no seu computador.<br>

Na próxima etapa vamos adicionar o caminho para o sistema reconhecer o rclone.<br>
Aperte o botão do windows no teclado e digite “variáveis de ambiente” e pressione enter.<br>
Na janela que for aberta, dê 2 cliques em “Path”.<br>
![Entrar nos caminhos do path](img/img8.png) <br>

Na nova janela, clique em “novo” e cole o endereço da pasta que copiamos anteriormente.<br>
![Adicionar ao path](img/img9.png)<br>

Aperte “ok” e feche as interfaces que foram abertas.<br>

__1.1.3__ <br>
 Aperte o botão do windows e digite “PowerShell”. Do lado direito do resultado, clique em “executar como administrador”. <br>
![Abrir powerShell como adm](img/img10.png) <br>




