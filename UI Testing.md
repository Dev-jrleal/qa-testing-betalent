# Plano de Testes: [UI Testing da Plataforma Sauce Demo]

### Introdução:
*Este documento relaciona os casos de uso a serem testados, é focado à interface de usuário (UI) da plataforma Sauce Demo, analizando aspectos funcionais,visuais e de usabilidade para garantir a consistência e a qualidade da aplicação.*

### Escopo:

O escopo desse projeto de teste, tem como objetivo, o levantamento de cenários e as especificações dos casos de teste.

> :memo: **Verificar os elementos da interface na página de login, página de produtos e checkout.**

> :memo: **Garantir a responsividade em diferentes dispositivos.**

> :memo: **Avaliar a interação do usuário com os componentes.**

O projeto engloba também a descrição dos bugs encontrados, conforme os casos de teste, e como eles acontecem.
É descrito também algumas melhorias de layout e usabilidade, para que os fluxos do sistema sejam mais bem aproveitados pelo o usuário. No final do documento, é apresentada a automação, as funcionalidade que ela aborda e os cenários que estão automatizados.

## Casos de Teste:

### **Página de Login**
|`` ID   ``| Caso de Teste                                | Etapas                                                                 | Resultado Esperado                                                             | Critério de Sucesso              |
|------|---------------------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------|----------------------------------|
| TC01 | Verificar a exibição dos elementos da página | 1. Acessar a página de login<br>2. Validar se os campos "Username", "Password" e botão "Login" estão visíveis | Os elementos devem ser exibidos corretamente com alinhamento e responsividade | Todos os elementos visíveis e alinhados |
| TC02 | Verificar o comportamento com credenciais válidas | 1. Inserir `standard_user` e senha correta<br>2. Clicar no botão "Login" | Redirecionar para a página de produtos                                         | Redirecionamento bem-sucedido    |
| TC03 | Verificar mensagem de erro com credenciais inválidas | 1. Inserir credenciais incorretas<br>2. Clicar no botão "Login"         | Exibir mensagem de erro "Epic sadface: Username and password do not match"     | Mensagem exibida corretamente    |
| TC04 | Verificar comportamento com campo vazio | 1. Deixar campo em branco<br>2. Clicar no botão "Login" | Exibir mensagem de erro "Epic sadface: Username is required" | Mensagem exibida corretamente

### **Página de Produtos**
| ID   | Caso de Teste                     | Etapas                                                                | Resultado Esperado                                                             | Critério de Sucesso              |
|------|-----------------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|----------------------------------|
| TC05 | Validar a exibição da lista de produtos | 1. Acessar a página de produtos<br>2. Verificar se todos os itens são exibidos com nome, imagem, preço e botão "Add to cart" | Todos os itens devem ser exibidos corretamente                                | Dados exibidos de forma clara e alinhada |
| TC06 | Testar funcionalidade de ordenação de produtos | 1. Selecionar "Price (low to high)" no dropdown<br>2. Verificar a ordenação da lista | Os produtos devem ser ordenados por preço, do menor para o maior              | Ordenação correta e responsiva |

### **Checkout**
| ID   | Caso de Teste                     | Etapas                                                                | Resultado Esperado                                                             | Critério de Sucesso              |
|------|-----------------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|----------------------------------|
| TC07 | Adicionar produto ao carrinho     | 1. Clicar no botão "Add to cart" de um produto<br>2. Validar a atualização do contador no ícone do carrinho | Contador do carrinho incrementado                                             | Contador exibindo o número correto |
| TC08 | Remover produto do carrinho       | 1. Clicar no botão "Remove" de um produto já adicionado<br>2. Validar a atualização do contador no ícone do carrinho | Contador do carrinho decrementado ou removido se vazio                        | Atualização do contador em tempo real |
| TC09 | Finalizar a compra | 1. Clicar no botão "Checkout"<br>2. Preencher com as informações do usuário: First Name, Last Name e Zip/Postal Code<br>3. Clicar no botão "Continue" | Descrição completa da compra, com as informações: Payment Information, Shipping Information, Price Total e Total<br>Duas opções: "Cancel" ou "Finish" | Ao clicar em "Finish" a menssagem sera exibida:"Thank you for your order!"<br>Botão "Back Home" |
| TC10 | Verificar a mensagem de erro ao finalizar a compra com campos vazios | 1. Clicar no botão "Checkout"<br>2. Clicar no botão "Cantinue" | Exibir mensagem de erro "Error: First Name is required" | Mensagem exibida corretamente |

## **Sugestões de Melhorias de UX/UI**
 **Filtro de produtos**: Melhorar a lógica de aplicação para evitar erros na seleção de categorias.
 **Página de erro 404**: Criar uma página mais amigável para lidar com redirecionamentos incorretos.
 **Confirmação de logout**: Adicionar um modal de confirmação para evitar logouts acidentais.

## **Lista de Bugs Encontrados**
**Bug01**: Filtros de produtos não aplicam categorias corretamente.
**Bug02**: Link "About" redireciona para uma página [saucelabs.com].
**Bug03**: Botão "Logout" não exibe modal de confirmação.

## **Análise de Riscos**
> :warning: **Impacto na navegação**: Links quebrados podem prejudicar a experiência do usuário e reduzir a confiança na plataforma.
> :warning: **Erro no filtro de produtos**: Usuários podem não encontrar os itens desejados, resultando em perda de vendas.
> :warning: **Ausência de confirmação de logout**: Pode levar a frustrações se usuários forem desconectados acidentalmente.

## **Extras**

### **Testes de Responsividade**
- Testado em dispositivos móveis (iPhone, Android) e em telas menores.  
**Resultado**: ✅ Layout responsivo e adaptado.

### **Testes de Acessibilidade**
- Testado com **Lighthouse**.  
**Resultado**: ⚠️ Sugere melhorias em contraste de texto e atributos ALT em imagens.

### **Sugestões de Automação**
*Automatizar os seguintes cenários críticos:*
Login com diferentes tipos de usuários.
Fluxo completo de compra.
Testes de navegação para garantir links funcionais.

### **Dificuldades Encontrada**
- **Tempo de execução**: Testes demoraram mais do que o previsto.
- **Limitações de recursos**: Faltaram recursos para realizar testes em diferentes dispositivos

## **Conclusão**
A plataforma está funcional para a maioria dos fluxos críticos, mas ajustes são necessários para aprimorar a experiência do usuário e corrigir bugs identificados.
