# Divi Child (Tema filho de Divi)

O WordPress possibilita a criação de um [tema filho (Child Themes)](https://codex.wordpress.org/Child_Themes), para tal, foram desenvolvidas as funções nos arquivos abaixo:

## functions.php

### ja_remove_hentry;

Como citado na [Wiki](https://github.com/gustavofersilva/drfabioafernandes/wiki/Tecnologias-utilizadas), foi utilizada a tecnologia [Google Structured Data](https://developers.google.com/search/docs/guides/intro-structured-data). Porém havia um bug no tema no qual a classe hentry do WordPress estava sendo reconhecida como um dado estruturado pelo Google, pois a mesma gera uma espécie de microdados, porém diferentes do atual padrão que os buscadores utilizam que é o [schema.org](https://schema.org) o que atrapalhava no parseamento correto do site pelo Google. Por isso, essa função remove a ação realizada pela classe hentry eliminando assim o problema.

## header.php

O WordPress permite a criação de [Campos Personalizados (Custom Fields)](https://codex.wordpress.org/Custom_Fields). Como foi necessário realizar a serialização de partes dos dados de arquivos, foi desenvolvido um campo denominado schema no qual as informações em JSON-LD são inseridas e armezenadas no banco de dados, e o WordPress se encarrega de recuperar as informações do banco e chamar a [função echo](https://secure.php.net/manual/pt_BR/function.echo.php), escrevendo assim dentro da tag head do HTML da página. 


