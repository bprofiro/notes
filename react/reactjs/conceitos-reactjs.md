# Conceitos ReactJS
## Componentização
-> Sempre que vamos fazer um component, temos que importar o React.
  -> Exemplo de component:

```jsx
import React, { ButtonHTMLAttributes } from 'react';

type ButtonProps = ButtonHTMLAttributes<HTMLButtonElement>;

const Button: React.FC<ButtonProps> = ({ children, ...rest }) => (
  <Button type="button" {...rest}>
    {children}
  </Button>
);

export default Button;
```

## Propriedades
-> Alguma informação que podemos passar de um component pai para o component
filho.
-> Para pegar algum component de uma tag HTML, devemos importar como  parâmetro
`children` e passar ele dentro do component filho `{children}`.

## Estado e Imutabilidade
-> Garante performace mesmo em aplicações com muitos dados.
`useState()` -> Retorna um Array com duas posições:
  - Primeira posição: Variável com seu valor inicial.
  - Segunda posição: Função para atualizar esse valor.

```jsx
const [projects, setProjects] = useState();
```