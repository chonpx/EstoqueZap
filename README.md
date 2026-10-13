# EstoqueZap MatCon — Controle de Estoque via WhatsApp para Lojas de Materiais de Construção

Este repositório contém a documentação e o código de um MVP (Minimum Viable Product) desenvolvido como parte de um projeto prático de aplicação de tecnologia e inteligência artificial para o varejo tradicional. 

A aplicação está publicada e acessível em: **[https://inventory-chat-link.lovable.app/](https://inventory-chat-link.lovable.app/)**

---

## 1. A Dor Escolhida e Por Que Ela Vale um Negócio

### O Problema (A Dor)
As lojas de materiais de construção de pequeno e médio porte (comércio de bairro, depósitos e ferragens) sofrem com um gargalo operacional crítico: **a desconexão entre o estoque físico (pátio/fundos) e o atendimento (balcão/caixa)**. 
* Os sistemas de gestão tradicionais (ERPs) são engessados, exigindo que o estoquista pare o que está fazendo, vá até um computador e navegue por telas complexas para registrar entradas de mercadorias ou baixas por avarias.
* Na correria do dia a dia, os funcionários simplesmente **não atualizam o sistema**, gerando divergências crônicas de inventário (*"o sistema diz que tem, mas na prateleira acabou"*), perda de vendas no balcão e prejuízos invisíveis com rupturas.

### Por que vale um negócio?
Trata-se de um mercado extremamente pulverizado, analógico e de margens apertadas. Resolver a fricção do lançamento de dados eliminando a necessidade de computadores e permitindo a gestão direto pelo **WhatsApp** (ferramenta que os funcionários já dominam e usam no dia a dia) gera um ganho imediato de produtividade, evita perdas financeiras e reduz drasticamente a barreira de adoção tecnológica (*onboarding zero*) para o chão de loja.

---

## 2. Tamanho de Mercado e Business Model Canvas

### Dimensionamento (Mercado Brasileiro)
* **TAM (Total Addressable Market):** O mercado total de varejo de materiais de construção no Brasil é de aproximadamente **160.000 estabelecimentos** (dados da ANAMACO), totalizando um mercado potencial de **R$ 480 milhões/ano** (considerando um ticket médio SaaS de R$ 3.000/ano por CNPJ).
* **SAM (Serviceable Available Market):** Recortando para PMEs estruturadas com funcionários e depósitos físicos ativos, estimamos cerca de **96.000 lojas** (**R$ 288 milhões/ano**).
* **SOM (Serviceable Obtainable Market):** Focando nos primeiros 12 a 24 meses em praças de validação inicial regional (como o estado do Rio de Janeiro e focos estratégicos em Niterói), miramos capturar **1% do SAM**, alcançando **~960 lojas** (~R$ 2,88 milhões/ano).

### Business Model Canvas resumido

| Componente | Resumo Estratégico |
| :--- | :--- |
| **Segmento de Clientes** | Donos, gerentes, estoquistas e balconistas de depósitos de materiais de construção de pequeno e médio porte. |
| **Proposta de Valor** | Estoque sem atrito via WhatsApp (áudio ou texto), zero ruptura no balcão e implementação rápida sem sistemas complexos. |
| **Canais** | Abordagem de campo local (*porta a porta* em Niterói), indicações entre lojistas e captação via formulário web integrado. |
| **Fontes de Receita** | Modelo **SaaS Recorrente** (assinatura mensal por CNPJ, variando de R$ 197 a R$ 347/mês) + taxa opcional de migração de dados. |
| **Recursos-Chave** | WebApp, banco de dados em nuvem (Supabase) e motor de IA conversacional para interpretação de mensagens de pátio. |
| **Estrutura de Custos** | Infraestrutura de servidores em nuvem, consumo de APIs de WhatsApp/IA e tempo de suporte/vendas locais. |

---

## 3. A Tese do MVP e O Que Ficou Manual de Propósito

### A Tese Testada
> *"Funcionários de chão de loja em depósitos de construção atualizarão o estoque com muito mais fidelidade se puderem fazer isso de forma conversacional (por texto ou áudio rápido no WhatsApp) do que se precisarem interagir com um software de gestão tradicional."*

### O Que Ficou Manual de Propósito (Abordagem Wizard of Oz)
Para validar a demanda e o comportamento do usuário antes de investir meses de desenvolvimento em engenharia de automação de APIs oficiais do WhatsApp e motores complexos de IA de áudio, escolhemos manter deliberadamente manuais:
1. **O Processamento de Entradas/Baixas:** No protótipo inicial de validação de campo (*field test*), as interações simuladas demonstram a facilidade de uso, mas podem ser operadas ou supervisionadas de forma assistida para medir o engajamento real do estoquista antes da automação pesada por IA conversacional.
2. **O Atendimento Comercial de Leads:** O formulário preenchido por novos lojistas interessados na plataforma dispara alertas internos para que o administrador realize o primeiro contato comercial de forma consultiva e direta via WhatsApp.

---

## 4. O Mega Prompt e as Correções Posteriores

### O Mega Prompt Inicial (Utilizado no Lovable)
```text
"Crie um aplicativo web responsivo em React com Tailwind CSS e componentes shadcn-ui para um MVP completo de controle e gerenciamento de estoque de materiais de construção via chatbot de WhatsApp chamado 'EstoqueZap MatCon'.

O app deve conter as seguintes funcionalidades integradas:
1. BARRA SUPERIOR (NAVBAR): Logotipo 'EstoqueZap MatCon' e ícone de engrenagem/administração no canto superior direito.
2. TELA PRINCIPAL (SIMULADOR DO WHATSAPP + OPERAÇÃO): Chat interativo simulando o bot nos 4 cenários (Entrada de mercadoria da Tigre, Consulta rápida de preço/saldo da Argamassa Quartzolit, Baixa por avaria de cimento Mauá, e Alerta proativo de estoque crítico do Vedacit).
3. PAINEL ADMINISTRATIVO: Tabela completa de gestão de estoque estruturada para o setor de MatCon (SKU, Nome, Categoria, Unidade de Medida, Qtd Atual, Estoque Mínimo com alerta visual, Localização no pátio e Preço de Tabela) com dados iniciais populados.
4. FORMULÁRIO DE CAPTURA DE LEADS (ONBOARDING DE LOJAS): Seção para preenchimento de dados de novas lojas (focado inicialmente em Niterói/RJ)."
````
<img width="1279" height="901" alt="image" src="https://github.com/user-attachments/assets/d37e6b0e-1393-4231-b4bb-13629db4f5b3" />

<img width="1275" height="901" alt="image" src="https://github.com/user-attachments/assets/11063557-63da-44e6-91e0-5fedbaaa5002" />

<img width="1273" height="746" alt="image" src="https://github.com/user-attachments/assets/50230125-3f6d-4e03-8dbc-075335f85ceb" />


