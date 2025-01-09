# WordPress Child Theme - Custom Login Page

Este repositório contém o código para um tema filho do WordPress, focado na personalização da página de login padrão. Ele permite alterar o estilo da página de login por meio de CSS personalizado e adicionar funcionalidades específicas utilizando o arquivo `functions.php`.

## Descrição

Este tema filho foi desenvolvido para simplificar a personalização da página de login do WordPress, oferecendo um ponto de partida para desenvolvedores que desejam alterar o estilo e o comportamento dessa página sem modificar diretamente o tema principal. Com suporte para CSS customizado e funcionalidades adicionais via `functions.php`, você pode criar uma experiência de login totalmente única e alinhada à identidade visual do seu projeto.

## Funcionalidades

- Personalização completa do CSS da página de login.
- Inclusão de código no `functions.php` para integrar as alterações.
- Pronto para ser adaptado a diferentes projetos WordPress.

## Estrutura do Repositório

```
├── style.css                # Estilo personalizado para a página de login
├── functions.php            # Funções adicionais para customização
└── README.md                # Documentação do repositório
```

## Como Usar

1. **Criação do Tema Filho:**
   - Crie uma pasta na raiz do diretório de temas do WordPress (wp-content/themes).
   - Nomeie a pasta conforme o tema desejado (ex: `custom-login-child`).

2. **Adicione os Arquivos:**
   - Copie os arquivos `style.css` e `functions.php` deste repositório para a pasta criada.

3. **Configure o Tema Filho:**
   - Certifique-se de incluir o cabeçalho do tema filho no `style.css`:
     ```css
     /*
     Theme Name: Custom Login Child
     Template: [nome-do-tema-pai]
     */
     ```
     Substitua `[nome-do-tema-pai]` pelo diretório do tema pai.

4. **Ative o Tema Filho:**
   - Acesse o painel administrativo do WordPress.
   - Vá em **Aparência > Temas** e ative o tema filho.

5. **Personalize a Página de Login:**
   - Edite o arquivo `style.css` para ajustar o visual da página de login.
   - Adicione ou modifique funções no `functions.php` conforme necessário.

## Exemplo de Alteração no CSS

```css
/* Exemplo de alteração no estilo da página de login */
body.login {
    background-color: #f0f0f0;
}

.login h1 a {
    background-image: url('caminho-para-seu-logo.png');
    background-size: contain;
    width: 300px;
    height: 80px;
}
```

## Exemplo de Função no functions.php

```php
<?php
// Adicionar o CSS personalizado na página de login
function custom_login_css() {
    wp_enqueue_style('custom-login', get_stylesheet_directory_uri() . '/style.css');
}
add_action('login_enqueue_scripts', 'custom_login_css');

// Alterar a URL do logo na página de login
function custom_login_logo_url() {
    return home_url();
}
add_filter('login_headerurl', 'custom_login_logo_url');
?>
```

## Contribuição

Sinta-se à vontade para contribuir com melhorias ou correções. Envie um pull request ou abra uma issue para discutirmos.

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
