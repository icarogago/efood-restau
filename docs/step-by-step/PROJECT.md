# Documentação do Projeto eFood

## Visão Geral

O eFood é um sistema de delivery de comida desenvolvido com React, TypeScript e Redux Toolkit. O projeto segue uma arquitetura moderna e escalável, com foco em manutenibilidade e performance.

## Stack Tecnológica

- **Frontend**: React + TypeScript
- **Gerenciamento de Estado**: Redux Toolkit
- **Estilização**: Styled Components
- **Roteamento**: React Router
- **Requisições HTTP**: RTK Query

## Estrutura do Projeto

### Diretórios Principais

```
src/
├── assets/        # Recursos estáticos (imagens, ícones)
├── components/    # Componentes reutilizáveis
├── containers/    # Componentes com lógica de estado
├── global/        # Estilos globais
├── pages/         # Páginas da aplicação
├── routes/        # Configuração de rotas
├── services/      # Serviços e APIs
├── store/         # Configuração do Redux
└── utils/         # Funções utilitárias
```

### Componentes Principais

- **Button**: Componente base para botões
- **Card**: Exibição de itens (restaurantes, produtos)
- **Footer**: Rodapé da aplicação
- **Hero**: Seção principal da página inicial
- **Logo**: Logo da aplicação
- **Modal**: Componentes modais
- **Tag**: Tags/categorias

### Páginas

- **Home**: Listagem de restaurantes
- **Perfil**: Gerenciamento de perfil do usuário

## Tipos de Dados

### MenuDataProps

```typescript
{
  id: number
  nome: string
  descricao: string
  foto: string
  porcao: string
  preco: number
}
```

### RestaurantsDataProps

```typescript
{
  id: number
  titulo: string
  avaliacao: string
  destacado: boolean
  tipo: string
  descricao: string
  capa: string
  cardapio: MenuDataProps[]
}
```

### DeliveryDataProps

```typescript
{
  receiver: string
  address: {
    description: string
    city: string
    zipCode: string
    number: number
    complement: string
  }
  payment: {
    name: string
    cardNumber: string
    code: string
    expires: {
      month: string
      year: string
    }
  }
}
```

## Fluxo de Dados

### Gerenciamento de Estado

- **Redux Store**: Estado global da aplicação
- **Cart Reducer**: Gerenciamento do carrinho de compras
- **API Integration**: RTK Query para chamadas à API

### Fluxo de Compra

1. Seleção de restaurante
2. Visualização do cardápio
3. Adição de itens ao carrinho
4. Checkout com dados de entrega
5. Processamento de pagamento

## Boas Práticas

### Código

- Tipagem forte com TypeScript
- Componentização
- Separação de responsabilidades
- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple, Stupid)

### Estado

- Gerenciamento centralizado com Redux
- Imutabilidade de dados
- Normalização de estado

### Performance

- Lazy loading de componentes
- Memoização quando necessário
- Otimização de re-renders

## Convenções

### Nomenclatura

- Componentes: PascalCase
- Funções: camelCase
- Tipos/Interfaces: PascalCase com sufixo Props
- Arquivos de componentes: PascalCase
- Arquivos de utilidades: camelCase

### Estrutura de Componentes

```typescript
// Importações
import { ... } from '...'

// Tipos
type ComponentProps = {
  // props
}

// Componente
const Component = ({ prop1, prop2 }: ComponentProps) => {
  // lógica
  return (
    // JSX
  )
}

export default Component
```

## Manutenção e Escalabilidade

### Adição de Novos Recursos

1. Criar tipos necessários em `types.d.ts`
2. Implementar componentes em `/components`
3. Adicionar lógica de estado em `/store/reducers`
4. Criar serviços em `/services`
5. Implementar rotas em `/routes`

### Refatoração

- Manter componentes pequenos e focados
- Extrair lógica complexa para hooks customizados
- Utilizar padrões de projeto quando apropriado
- Manter testes atualizados

## Considerações de Segurança

- Validação de dados de entrada
- Sanitização de dados
- Proteção contra XSS
- Validação de formulários
- Tratamento de erros

## Performance

- Code splitting
- Lazy loading
- Otimização de imagens
- Caching de dados
- Minimização de re-renders

## Próximos Passos Sugeridos

1. Implementar testes unitários
2. Adicionar documentação de componentes
3. Implementar CI/CD
4. Otimizar performance
5. Adicionar analytics
6. Implementar PWA
