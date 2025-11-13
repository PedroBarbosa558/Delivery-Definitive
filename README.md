# Delivery-Definitive 🍔

Um aplicativo completo de **gerenciamento de pedidos e entregas** desenvolvido com Django. Sistema inteligente para restaurantes, lanchonetes e serviços de delivery com funcionalidades avançadas de pedidos, produtos e pagamentos.

---

## 📋 Funcionalidades

### 🛍️ Gerenciamento de Produtos
- ✅ Cadastro e gerenciamento de produtos
- ✅ Organização por categorias
- ✅ Upload de imagens dos produtos
- ✅ Descrição detalhada e ingredientes
- ✅ Sistema de adicionais e opções personalizadas
- ✅ Controle de disponibilidade (ativo/inativo)
- ✅ Gestão de preços com acréscimos para adicionais

### 🛒 Carrinho de Compras
- ✅ Adição de produtos ao carrinho
- ✅ Seleção de adicionais e opções personalizadas
- ✅ Cálculo automático de preço com acréscimos
- ✅ Visualização do carrinho em tempo real
- ✅ Gerenciamento de quantidade de itens

### 📦 Gerenciamento de Pedidos
- ✅ Finalização de pedidos com dados de entrega
- ✅ Registro de endereço completo (CEP, rua, número, bairro)
- ✅ Ponto de referência para melhor localização
- ✅ Registro de contato (telefone)
- ✅ Armazenamento de itens do pedido com detalhes
- ✅ Histórico de pedidos do usuário
- ✅ Status de entrega (entregue/pendente)

### 💳 Sistema de Pagamento
- ✅ Múltiplos métodos de pagamento (Dinheiro e Cartão)
- ✅ Cálculo automático de troco para pagamentos em dinheiro
- ✅ Integração com sistema de cupons de desconto

### 🎟️ Sistema de Cupons e Descontos
- ✅ Cadastro de cupons de desconto
- ✅ Aplicação de percentuais de desconto
- ✅ Controle de uso de cupons
- ✅ Ativação/desativação de cupons
- ✅ Rastreamento de quantas vezes cada cupom foi utilizado

### 👤 Autenticação e Perfil de Usuário
- ✅ Sistema de cadastro de clientes
- ✅ Login seguro com Django Auth
- ✅ Perfil de usuário extensível
- ✅ Associação de pedidos ao usuário

### 📱 Interface Responsiva
- ✅ Design amigável e intuitivo
- ✅ Templates HTML estruturados
- ✅ Filtros customizados para templates
- ✅ Sistema de categorias para navegação

---

## 🏗️ Arquitetura do Projeto

```
Delivery-Definitive/
├── delivery/                 # Configurações principais do Django
│   ├── settings.py          # Configurações do projeto
│   ├── urls.py              # Roteamento principal
│   └── wsgi.py              # Deploy em produção
├── produto/                 # App de produtos
│   ├── models.py            # Modelos (Produto, Categoria, Adicional)
│   ├── views.py             # Lógica de visualização
│   ├── urls.py              # Roteamento de produtos
│   ├── templates/           # Templates HTML
│   │   ├── home.html        # Página inicial
│   │   ├── produto.html     # Detalhes do produto
│   │   ├── carrinho.html    # Carrinho de compras
│   │   └── ver_carrinho.html # Visualização do carrinho
│   └── templatestags/       # Filtros customizados
├── pedido/                  # App de pedidos
│   ├── models.py            # Modelos (Pedido, ItemPedido, CupomDesconto)
│   ├── views.py             # Lógica de pedidos
│   ├── urls.py              # Roteamento de pedidos
│   └── templates/           # Templates HTML
│       ├── finalizar_pedido.html
│       ├── pedido_realizado.html
│       ├── cadastro_cliente.html
│       └── login.html
├── templates/               # Templates base
│   └── base.html            # Layout principal
├── media/                   # Arquivos enviados (imagens)
└── manage.py               # Utilitário de gerenciamento Django
```

---

## 🛠️ Tecnologias Utilizadas

- **Framework**: Django 5.2.6
- **Banco de Dados**: SQLite3
- **Frontend**: HTML5, CSS3, JavaScript
- **Autenticação**: Django Auth
- **Sistema de Templates**: Django Templates
- **Upload de Arquivos**: Django ImageField

---

## 📊 Modelos de Dados

### Produto
- Nome, descrição, ingredientes
- Preço e imagem
- Categoria associada
- Adicionais disponíveis
- Status (ativo/inativo)

### Pedido
- Usuário, valor total, método de pagamento
- Dados de entrega (endereço, CEP, telefone)
- Ponto de referência
- Cupom de desconto aplicado
- Status de entrega

### ItemPedido
- Produto associado
- Quantidade e preço unitário
- Descrição e adicionais

### CupomDesconto
- Código único
- Percentual de desconto
- Contador de usos
- Status (ativo/inativo)

### Categoria
- Nome da categoria

### Adicional
- Nome da opção
- Limite mínimo e máximo de seleções
- Opções disponíveis com acréscimos

---

## 🚀 Instalação e Execução

### Pré-requisitos
- Python 3.8+
- pip (gerenciador de pacotes Python)

### Passos para instalar

1. **Clone o repositório**
```bash
git clone https://github.com/PedroBarbosa558/Delivery-Definitive.git
cd Delivery-Definitive
```

2. **Crie um ambiente virtual**
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows
```

3. **Instale as dependências**
```bash
pip install -r requirements.txt
```

4. **Execute as migrações**
```bash
python manage.py migrate
```

5. **Crie um superusuário (admin)**
```bash
python manage.py createsuperuser
```

6. **Execute o servidor de desenvolvimento**
```bash
python manage.py runserver
```

7. **Acesse a aplicação**
- Aplicação: http://localhost:8000
- Painel Admin: http://localhost:8000/admin

---

## 📝 Como Usar

### Para Clientes
1. Navegue pela home e explore as categorias
2. Selecione um produto e customize com adicionais
3. Adicione ao carrinho
4. Finalize o pedido com seus dados de entrega
5. Escolha o método de pagamento
6. Aplique um cupom de desconto (opcional)
7. Confirme o pedido

### Para Administradores
1. Acesse o painel admin (`/admin`)
2. Cadastre produtos, categorias e adicionais
3. Gerencie cupons de desconto
4. Acompanhe os pedidos e marque como entregues

---

## 🔐 Segurança

- Integração com Django Auth para autenticação segura
- Proteção CSRF em formulários
- Gerenciamento seguro de sessões
- Validação de dados no servidor

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 👨‍💻 Autor

**Pedro Barbosa**
- GitHub: [@PedroBarbosa558](https://github.com/PedroBarbosa558)

---

## 💡 Funcionalidades Futuras

- [ ] Integração com pagamento online
- [ ] Notificações de status de pedido
- [ ] Avaliações e comentários de clientes
- [ ] Relatórios de vendas
- [ ] Sistema de rastreamento em tempo real
- [ ] App móvel
- [ ] Integração com APIs de delivery

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se livre para abrir issues e pull requests.

---

## 📞 Suporte

Para dúvidas ou sugestões, entre em contato ou abra uma issue no repositório.