# Manual de Virtualização do Lubuntu com Oracle VirtualBox

## 1. Download da Imagem ISO do Lubuntu

1. Acessar o site oficial do Lubuntu.
2. Realizar o download da versão desejada em formato ISO.
3. Salvar o arquivo em uma pasta de fácil acesso.

---

## 2. Criação da Máquina Virtual

### Passo 1: Criar uma nova máquina

1. Abrir o Oracle VirtualBox.
2. Clicar em **"Novo"**.
3. Definir:

   * Nome: Lubuntu;
   * Tipo: Linux;
   * Versão: Ubuntu (64 bits).

### Passo 2: Configurar a memória RAM

1. Definir a quantidade de memória RAM para a máquina virtual.
2. Recomenda-se utilizar pelo menos 2 GB para um funcionamento adequado do Lubuntu.

### Passo 3: Criar o disco virtual

1. Selecionar **"Criar um disco rígido virtual agora"**.
2. Escolher o formato **VDI**.
3. Selecionar armazenamento dinamicamente alocado.
4. Definir o tamanho do disco virtual (mínimo recomendado de 20 GB).
5. Finalizar a criação.

---

## 3. Configuração da ISO do Lubuntu

1. Selecionar a máquina virtual criada.
2. Acessar **Configurações → Armazenamento**.
3. Selecionar a unidade óptica virtual.
4. Escolher o arquivo ISO do Lubuntu.
5. Salvar as configurações.

---

## 4. Instalação do Lubuntu

1. Iniciar a máquina virtual.
2. Aguardar o carregamento da ISO.
3. Selecionar a opção **"Install Lubuntu"**.
4. Escolher:

   * Idioma;
   * Layout do teclado;
   * Fuso horário;
   * Nome de usuário;
   * Senha de acesso.
5. Selecionar a instalação utilizando todo o disco virtual criado.
6. Aguardar a conclusão da instalação.
7. Reiniciar a máquina virtual quando solicitado.

---

## 5. Instalação do VirtualBox Guest Additions

Após a instalação do Lubuntu, recomenda-se instalar o pacote Guest Additions para melhorar a integração entre o sistema hospedeiro e a máquina virtual.

### Benefícios

* Melhor desempenho gráfico;
* Ajuste automático da resolução da tela;
* Compartilhamento de área de transferência;
* Compartilhamento de pastas entre host e guest;
* Melhor suporte ao mouse e teclado.

---

## 6. Testes Realizados

Após a instalação do Lubuntu, foram realizados os seguintes testes:

* Inicialização correta do sistema operacional;
* Acesso ao ambiente gráfico LXQt;
* Funcionamento da conexão com a internet;
* Utilização do terminal Linux;
* Navegação em arquivos e diretórios;
* Funcionamento dos periféricos virtuais.

##
