# Jointjs para integração com o ScriptCase

![Tela de exemplo](./tela.png)

Este é um código PHP feito para permitir adicionar a classe JavaScript 
Jointjs de forma simples a aplicações feitas em ScriptCase.

Para esta primeira versão, você ira necessitar de um arquivo de fonte
true type para que os cálculos de tamanho possam ser feitos.

## Instalação

Abra o arquivo index.php e procura pelos dois comentários, "Código PHP a 
ser copiado e colado - início/fim" e copie este trecho de código em sua
aplicação ScriptCase.

Adicione os links das classes e css necessários ao código html. Página HTML.
```
<link rel="stylesheet" type="text/css" href="./css/dev/joint.css" />
<script src="./js/jquery.min.js"></script>
<script src="./js/lodash.min.js"></script>
<script src="./js/backbone-min.js"></script>
<script src="./js/dev/joint.js"></script>
```

Monte um script onReady() com a ajuda do JQuery. Página HTML.
```
<script>
$(document).ready(
function() {
<?php print makeOnReadyFunction( $data, $setup, $listElementsToAddLArr, $listLinksIdsLArr ); ?>
});
</script>
```

Configure a parte visual de sua aplicação com os valores padrão. Script PHP.
```
$fontSizeDefaultLUInt = 12;
$spaceWidthBetweenTextAndBorderUInt = 50;
$spaceHeightBetweenTextAndBorder = 10;
$setup = array(
"fontFamily" => "./tahoma.ttf",
"perspectiveFontSizeDefault" => $fontSizeDefaultLUInt,
"perspectiveFontColorDefault" => "#555555",
"perspectiveStrokeDefaultColor" => "#000000",
"perspectiveFillDefaultColor" => "#DDDDDD",
"perspectiveStrokeWidth" => 0,
"perspectiveRx" => 1,
"perspectiveRy" => 1,
"perspectiveCircleCx" => 7,
"perspectiveCircleCy" => 7,
"perspectiveCircleCR" => 7,
"perspectiveCircleStroke" => "#000000",
"perspectiveCircleStrokeWidth" => 2,
"perspectiveCircleStrokeFill" => "#00FF00",
"perspectiveSpaceWidthBetweenTextAndBorder" => $spaceWidthBetweenTextAndBorderUInt - 10,
"perspectiveSpaceHeightBetweenTextAndBorder" => $spaceHeightBetweenTextAndBorder - 10,
"perspectiveSpaceUpper" => 20,
"perspectiveSpaceBottom" => 10,

"columnsFontSizeDefault" => $fontSizeDefaultLUInt,
"columnsFontColorDefault" => "#5555FF",
"columnsStrokeDefaultColor" => "#000000",
"columnsFillDefaultColor" => "#DDDDDD",
"columnsStrokeWidth" => 0,
"columnsRx" => 1,
"columnsRy" => 1,
"columnsCircleCx" => 7,
"columnsCircleCy" => 7,
"columnsCircleCR" => 7,
"columnsCircleStroke" => "#000000",
"columnsCircleStrokeWidth" => 2,
"columnsCircleStrokeFill" => "#FFFF00",
"columnsSpaceWidthBetweenTextAndBorder" => $spaceWidthBetweenTextAndBorderUInt - 10,
"columnsSpaceHeightBetweenTextAndBorder" => $spaceHeightBetweenTextAndBorder - 10,
"columnsSpaceWidthBetween" => 30,
"columnsSpaceBottom" => 10,

"objectivesFontSizeDefault" => $fontSizeDefaultLUInt,
"objectivesFontColorDefault" => "#3498DB",
"objectivesStrokeDefaultColor" => "#000000",
"objectivesFillDefaultColor" => "#2C3E50",
"objectivesStrokeWidth" => 2,
"objectivesRx" => 1,
"objectivesRy" => 1,
"objectivesCircleCx" => 7,
"objectivesCircleCy" => 7,
"objectivesCircleCR" => 7,
"objectivesCircleStroke" => "#000000",
"objectivesCircleStrokeWidth" => 2,
"objectivesCircleStrokeFill" => "#00FF00",
"objectivesSpaceWidthBetween" => 30,
"objectivesSpaceHeightBetween" => 20,
"objectivesSpaceWidthBetweenTextAndBorder" => $spaceWidthBetweenTextAndBorderUInt,
"objectivesSpaceHeightBetweenTextAndBorder" => $spaceHeightBetweenTextAndBorder

);
```

Monte um array de dados. Script PHP.
```
$data = array(
"link" => array(
  array(
    "id" => "unique_id_link_1",
    "link" => array(
      "from" => "unique_id_2",
      "to" => "unique_id_3"
    )
  ),
  array(
    "id" => "unique_id_link_2",
    "link" => array(
      "from" => "unique_id_4",
      "to" => "unique_id_3"
    )
  ),
  array(
    "id" => "unique_id_link_3",
    "link" => array(
      "from" => "unique_id_12",
      "to" => "unique_id_4"
    )
  ),
  array(
    "id" => "unique_id_link_4",
    "link" => array(
      "from" => "unique_id_11",
      "to" => "unique_id_12"
    )
  ),
  array(
    "id" => "unique_id_link_5",
    "link" => array(
      "from" => "unique_id_13",
      "to" => "unique_id_4"
    )
  ),
  array(
    "id" => "unique_id_link_6",
    "link" => array(
      "from" => "unique_id_20",
      "to" => "unique_id_2"
    )
  ),
  array(
    "id" => "unique_id_link_7",
    "link" => array(
      "from" => "unique_id_20",
      "to" => "unique_id_12"
    )
  ),
  array(
    "id" => "unique_id_link_8",
    "link" => array(
      "from" => "unique_id_21",
      "to" => "unique_id_12"
    )
  ),
  array(
    "id" => "unique_id_link_9",
    "link" => array(
      "from" => "unique_id_22",
      "to" => "unique_id_12"
    )
  ),
  array(
    "id" => "unique_id_link_10",
    "link" => array(
      "from" => "unique_id_23",
      "to" => "unique_id_12"
    )
  ),
  array(
    "id" => "unique_id_link_11",
    "link" => array(
      "from" => "unique_id_13",
      "to" => "unique_id_12"
    )
  )
),
"float" => array(
  array(
    "id" => "unique_id_float_1",
    "text" => "Eliminar o<br>desperdício de uso",
    "circleStrokeFill" => "#00FF00",
    "stroke" => "#AAAA00",
    "circleStroke" => "#AAAA00",
    "fill" => "#FFFF00",
    "x" => 10,
    "y" => 10
  )
),
"data" => array(
  array(
    "id" => "unique_id_1",
    "text" => "Financeira",
    "fill" => "#FFFF00",
    "fontColor" => "#3498DB",
    "objective" => array(
      array(
        array(
          "id" => "unique_id_2",
          "text" => "Eliminar o<br>desperdício de uso",
          "circleStrokeFill" => "#00FF00",
          "stroke" => "#AAAA00",
          "circleStroke" => "#AAAA00",
          "fill" => "#FFFF00"
        ),
        array(
          "id" => "unique_id_3",
          "text" => "Aumentar a rentabilidade da<br>instituição de forma sustentável",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#AA0000",
          "circleStroke" => "#AAAA00",
          "fill" => "#FFFF00"
        ),
        array(
          "id" => "unique_id_4",
          "text" => "Aumentar a receita de<br>forma diversificada",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#AA0000",
          "circleStroke" => "#AAAA00",
          "fill" => "#FFFF00"
        )
      )
    )
  ),
  array(
    "id" => "unique_id_10",
    "text" => "Mercado e Cliente",
    "fill" => "#2C3E50",
    "fontColor" => "#FFFFFF",
    "objective" => array(
      array(
        array(
          "id" => "unique_id_11",
          "text" => "Desenvolver a satisfação dos pacientes,<br>Estado, Município e Operadoras",
          "circleStrokeFill" => "#FFFF00",
          "fontColor" => "#FFFFFF",
          "stroke" => "#0000FF"
        ),
        array(
          "id" => "unique_id_12",
          "text" => "Apresentar uma imagem de<br>resolutividade para os problemas",
          "circleStrokeFill" => "#FF0000",
          "fontColor" => "#FFFFFF",
          "stroke" => "#0000FF"
        ),
        array(
          "id" => "unique_id_13",
          "text" => "Fidelizar o corpo clínico da instituição",
          "circleStrokeFill" => "#FF0000",
          "fontColor" => "#FFFFFF",
          "stroke" => "#FF0000"
        )
      )
    )
  ),
  array(
    "id" => "unique_id_19",
    "text" => "Processos internos",
    "fill" => "#FF7777",
    "fontColor" => "#FFFFFF",
    "columns" => array(
      array(
        "id" => "unique_id_col_1",
        "text" => "Gestão de mercado/cliente",
        "fill" => "#FF7777",
        "fontColor" => "#FFFFFF"
      ),
      array(
        "id" => "unique_id_col_2",
        "text" => "Pesquisa e Inovação",
        "fill" => "#FF7777",
        "fontColor" => "#FFFFFF"
      ),
      array(
        "id" => "unique_id_col_3",
        "text" => "Excelência Operacional",
        "fill" => "#FF7777",
        "fontColor" => "#FFFFFF"
      ),
      array(
        "id" => "unique_id_col_4",
        "text" => "Desenvolvimento social",
        "fill" => "#FF7777",
        "fontColor" => "#FFFFFF"
      )
    ),
    "objective" => array(
      array(
        //Gestão de mercado/cliente
        array(
          "id" => "unique_id_21",
          "text" => "Desenvolver atendimento<br>humanizado no corpo",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        //Pesquisa e Inovação
        array(
          "id" => "unique_id_23",
          "text" => "Incentivar o<br>desenvolvimento de novos",
          "circleStrokeFill" => "#FFFF00",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        //Excelência Operacional
        array(
          "id" => "unique_id_20",
          "text" => "Desenvolver a qualidade<br>de atendimento acima dos<br>padrões do mercado.",
          "circleStrokeFill" => "#FFFF00",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        //Desenvolvimento social
        array(
          "id" => "unique_id_22",
          "text" => "Aumentar número de<br>horas dedicadas a<br>projetos",
          "circleStrokeFill" => "#00FF00",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        )
      ),
      array(
        //Gestão de mercado/cliente
        array(
          "id" => "unique_id_25",
          "text" => "Criar estruturas para atuar<br>também nos segmentos<br>de camada social",
          "circleStrokeFill" => "#FFFF00",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        //Pesquisa e Inovação
        array(
          "id" => "unique_id_27",
          "text" => "Aumentar o número<br>de parcerias e<br>projetos com faculdades",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        //Excelência Operacional
        array(
          "id" => "unique_id_24",
          "text" => "Desenvolver a qualidade<br>da instituição de forma<br>continua para garantir<br>certificações adquiridas",
          "circleStrokeFill" => "#FFFF00",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        //Desenvolvimento social
        array(
          "id" => "unique_id_26",
          "text" => "Compartilhar a excelência<br>científica e em gestão com<br>instituições filantrópicas<br>da mesma área",
          "circleStrokeFill" => "#00FF00",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
      ),
      array(
        array(),
        //Gestão de mercado/cliente
        array(
          "id" => "unique_id_28",
          "text" => "Criar estreitamento<br>no relacionamento<br>com as...",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        ),
        array(),
        //Pesquisa e Inovação
        array(
          "id" => "unique_id_29",
          "text" => "Estimular a criação<br>de trabalhos científicos",
          "circleStrokeFill" => "#999999",
          "stroke" => "#FF0000",
          "fill" => "#FF7777",
          "fontColor" => "#FFFFFF"
        )
      )
    )
  ),
  array(
    "id" => "unique_id_31",
    "text" => "Aprendizado e Crescimento",
    "fill" => "#F781F3",
    "fontColor" => "#FFFFFF",
    "columns" => array(
      array(
        "id" => "unique_id_col_5",
        "text" => "Desenvolver o capital humano",
        "fill" => "#F781F3",
        "fontColor" => "#FFFFFF"
      ),
      array(
        "id" => "unique_id_col_6",
        "text" => "Capital organizacional",
        "fill" => "#F781F3",
        "fontColor" => "#FFFFFF"
      ),
      array(
        "id" => "unique_id_col_7",
        "text" => "Capital da organização",
        "fill" => "#F781F3",
        "fontColor" => "#FFFFFF"
      )
    ),
    "objective" => array(
      array(
        array(
          "id" => "unique_id_32",
          "text" => "Desenvolver a<br>motivação e inovação",
          "circleStrokeFill" => "#FFFF00",
          "stroke" => "#8904B1",
          "fill" => "#F781F3",
          "fontColor" => "#FFFFFF"
        ),
        array(
          "id" => "unique_id_33",
          "text" => "Desenvolver um clima<br>organizacional mais adequado",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#FF0000",
          "fill" => "#F781F3",
          "fontColor" => "#FFFFFF"
        ),
        array(
          "id" => "unique_id_34",
          "text" => "Alimentar e integrar as<br>informações para ajudar a ...",
          "circleStrokeFill" => "#FF0000",
          "stroke" => "#FF0000",
          "fill" => "#F781F3",
          "fontColor" => "#FFFFFF"
        )
      ),
      array(
        array(
          "id" => "unique_id_35",
          "text" => "Criar cultura<br>humanizante no corpo",
          "circleStrokeFill" => "#FFFF00",
          "stroke" => "#FF0000",
          "fill" => "#F781F3",
          "fontColor" => "#FFFFFF"
        )
      )
    )
  )
)
);
```

Na prática, você vai montar o array de dados com as informações passadas
pelo banco de dados.

**Cuidado:** Um **ID** deve ser único, começar por letra ou underline, e
não pode conter espaços ou caracteres especiais. Ele vai virar uma 
variável JavaScript.

Formato do array de dados:
```
$data = array(
  // Array bidimencional com todos os links
  // Links são as setas ligando os balões.
  [ opcional ] "link" => array(
    array(
      "id" => String - id único,
      "link" => array(
        "from" => String - id do elemento de partida,
        "to" => String - id do elemento de chegada
      )
    ),
    array(
      "id" => String - id único,
      "link" => array(
        "from" => String - id do elemento de partida,
        "to" => String - id do elemento de chegada
      )
    )
  ),
  // Array bidimencional com os elementos soltos
  // Float são balões flutuantes
  [ opcional ] "float" => array(
    array(
      "id" => String - id único,
      "text" => String - texto contido no balão,
      "x" => Unsigned Int - Coordenada x do balão,
      "y" => Unsigned Int - Coordenada y do balão,
      "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
      "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
      "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
      "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
    ),
    array(
      "id" => String - id único,
      "text" => String - texto contido no balão,
      "x" => Unsigned Int - Coordenada x do balão,
      "y" => Unsigned Int - Coordenada y do balão,
      "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
      "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
      "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
      "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
    )
  ),
  // Dados do gráfico
  "data" => array(
    // Dados da perspectiva
    // Um array por perspectiva
    array(
      // Dados da perspectiva
      "id" => String - id único,
      "text" => String - texto contido no balão,
      "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
      "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB",
      
      // A coluna fica entre a perspectiva e o objetivo
      [ opcional ] "columns" => array(
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        ),
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        ),
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        ),
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        )
      ),
      "objective" => array(
        // Um array por linha
        array(
        
          // Um array por balão/coluna
          array(
            "id" => String - id único,
            "text" => String - texto contido no balão,
            "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
            "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
            "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
            "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
          ),
          
          // Um array em branco para pular uma coluna.
          // Atenção, não se pode pular todas as colunas e deixar uma coluna inteira afastada
          array(),
          
          array(
            "id" => String - id único,
            "text" => String - texto contido no balão,
            "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
            "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
            "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
            "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
          )
        )
      )
    ),
  array(
      // Dados da perspectiva
      "id" => String - id único,
      "text" => String - texto contido no balão,
      "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
      "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB",
      [ opcional ] "columns" => array(
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        ),
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        ),
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        ),
        array(
          "id" => String - id único,
          "text" => String - texto contido no balão,
          "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00",
          "fontColor" => [ opcional ] String - cor da fonte do texto. Ex: "#3498DB"
        )
      ),
      "objective" => array(
        array(
          array(
            "id" => String - id único,
            "text" => String - texto contido no balão,
            "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
            "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
            "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
            "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
          ),
          array(
            "id" => String - id único,
            "text" => String - texto contido no balão,
            "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
            "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
            "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
            "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
          ),
          array(
            "id" => String - id único,
            "text" => String - texto contido no balão,
            "circleStrokeFill" => [ opcional ] String - cor do preenchimento do círculo. Ex: "#00FF00",
            "stroke" => [ opcional ] String - cor da linha. Ex: "#AAAA00",
            "circleStroke" => [ opcional ] String - cor da linha do círculo. Ex: "#AAAA00",
            "fill" => [ opcional ] String - cor do preenchimento. Ex: "#AAAA00"
          )
        )
      )
    )
  )
);
```

## Configurações

Para montar o gráfico, você necessita montar as configurações globais, e
sempre que necessários, você pode sobrescrever a configuração conforme as
tabelas abaixo.

### Configurações globais
|--------------------|-------------------------------------------------|
|fontFamily| Caminho do arquivo de fonte do servidor PHP |
|perspectiveFontSizeDefault| Tamanho padrão da fonte |
|perspectiveFontColorDefault| Cor padrão da fonte, ex.: #000000 |
|perspectiveStrokeDefaultColor| Cor padrão da linha, ex.: #000000 |
|perspectiveStrokeWidth| Espessura da linha de borda |
|perspectiveFillDefaultColor| Cor padrão do preenchimento, ex.: #FFFFFF |
|perspectiveRx| Raio x da curvatura da borda. 0 deixa quadrado, 1 dá uma leve quebra, n > 1 use com cuidado |
|perspectiveRy| Raio y da curvatura da borda. 0 deixa quadrado, 1 dá uma leve quebra, n > 1 use com cuidado |
|perspectiveCircleCx| Posição x do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|perspectiveCircleCy| Posição y do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|perspectiveCircleCR| Tamanho do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|perspectiveCircleStroke| Espessura da borda do círculo |
|perspectiveCircleStrokeWidth| Espessura da linha de borda |
|perspectiveCircleStrokeFill| Cor de preenchimento padrão do círculo. Ex. #FF0000 |
|perspectiveSpaceWidthBetweenTextAndBorder| Espaçamento horizontal entre o texto e a borda |
|perspectiveSpaceHeightBetweenTextAndBorder| Espaçamento vertical entre o texto e a borda |
|perspectiveSpaceUpper| Espaçamento superior entre os elementos |
|perspectiveSpaceBottom| Espaçamento inferior entre os elementos |
|columnsFontSizeDefault| Tamanho padrão da fonte |
|columnsFontColorDefault| Cor padrão da fonte, ex.: #000000 |
|columnsStrokeDefaultColor| Cor padrão da linha, ex.: #000000 |
|columnsStrokeWidth| Espessura da linha de borda |
|columnsFillDefaultColor| Cor padrão do preenchimento, ex.: #FFFFFF |
|columnsRx| Raio x da curvatura da borda. 0 deixa quadrado, 1 dá uma leve quebra, n > 1 use com cuidado |
|columnsRy| Raio y da curvatura da borda. 0 deixa quadrado, 1 dá uma leve quebra, n > 1 use com cuidado |
|columnsCircleCx| Posição x do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|columnsCircleCy| Posição y do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|columnsCircleCR| Tamanho do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|columnsCircleStroke| Espessura da borda do círculo |
|columnsCircleStrokeWidth| Espessura da linha de borda |
|columnsCircleStrokeFill| Cor de preenchimento padrão do círculo. Ex. #FF0000 |
|columnsSpaceWidthBetweenTextAndBorder| Espaçamento horizontal entre o texto e a borda |
|columnsSpaceHeightBetweenTextAndBorder| Espaçamento vertical entre o texto e a borda |
|columnsSpaceWidthBetween| Espaçamento horizontal entre as colunas [obsoleto] |
|columnsSpaceBottom| Espaçamento inferior entre os elementos |
|objectivesFontSizeDefault| Tamanho padrão da fonte |
|objectivesFontColorDefault| Cor padrão da fonte, ex.: #000000 |
|objectivesStrokeDefaultColor| Cor padrão da linha, ex.: #000000 |
|objectivesStrokeWidth| Espessura da linha de borda |
|objectivesFillDefaultColor| Cor padrão do preenchimento, ex.: #FFFFFF |
|objectivesRx| Raio x da curvatura da borda. 0 deixa quadrado, 1 dá uma leve quebra, n > 1 use com cuidado |
|objectivesRy| Raio y da curvatura da borda. 0 deixa quadrado, 1 dá uma leve quebra, n > 1 use com cuidado |
|objectivesCircleCx| Posição x do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|objectivesCircleCy| Posição y do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|objectivesCircleCR| Tamanho do círculo indicativo de status. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|objectivesCircleStroke| Espessura da borda do círculo |
|objectivesCircleStrokeWidth| Cor de preenchimento padrão do círculo. Ex. #FF0000 |
|objectivesCircleStrokeFill| Cor de preenchimento padrão do círculo. Ex. #FF0000 |
|objectivesSpaceWidthBetween| Espaçamento horizontal mínimo entre os balões. |
|objectivesSpaceHeightBetween| Espaçamento vertical mínimo entre os balões. |
|objectivesSpaceWidthBetweenTextAndBorder| Espaçamento horizontal entre o texto e a borda |
|objectivesSpaceHeightBetweenTextAndBorder| Espaçamento vertical entre o texto e a borda |

### Configurações individuais
|--------------------|-------------------------------------------------|
|id|[ obrigatório ] Id único obrigatório para cada elemento. Regra:[a-zA-Z__][a-zA-Z0-9__]* |
|stroke| [ opcional ] Cor da linha. |
|fill| [ opcional ] Cor do preenchimento. |
|strokeWidth| [ opcional ] Espessura da linha |
|rx| [ opcional ] Raio x da borda |
|ry| [ opcional ] Raio y da borda |
|fontSize| [ opcional ] Tamanho da fonte |
|fontColor| [ opcional ] Cor da fonte |
|circleCx| [ opcional ] Posição x do círculo. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|circleCy| [ opcional ] Posição y do círculo. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|circleCR| [ opcional ] Raio do círculo. Use Cx = Cy = CR para fazer um círculo no canto superior esquerdo |
|circleStroke| [ opcional ] Cor da borda |
|circleStrokeWidth| [ opcional ] Espessura da linha |
|circleStrokeFill| [ opcional ] Cor do preenchimento |

## Exemplo funcional
----------------------

```
<?php

  $data = array(
    "link" => array(
      array(
        "id" => "unique_id_link_1",
        "link" => array(
          "from" => "unique_id_2",
          "to" => "unique_id_3"
        )
      ),
      array(
        "id" => "unique_id_link_2",
        "link" => array(
          "from" => "unique_id_4",
          "to" => "unique_id_3"
        )
      ),
      array(
        "id" => "unique_id_link_3",
        "link" => array(
          "from" => "unique_id_12",
          "to" => "unique_id_4"
        )
      ),
      array(
        "id" => "unique_id_link_4",
        "link" => array(
          "from" => "unique_id_11",
          "to" => "unique_id_12"
        )
      ),
      array(
        "id" => "unique_id_link_5",
        "link" => array(
          "from" => "unique_id_13",
          "to" => "unique_id_4"
        )
      ),
      array(
        "id" => "unique_id_link_6",
        "link" => array(
          "from" => "unique_id_20",
          "to" => "unique_id_2"
        )
      ),
      array(
        "id" => "unique_id_link_7",
        "link" => array(
          "from" => "unique_id_20",
          "to" => "unique_id_12"
        )
      ),
      array(
        "id" => "unique_id_link_8",
        "link" => array(
          "from" => "unique_id_21",
          "to" => "unique_id_12"
        )
      ),
      array(
        "id" => "unique_id_link_9",
        "link" => array(
          "from" => "unique_id_22",
          "to" => "unique_id_12"
        )
      ),
      array(
        "id" => "unique_id_link_10",
        "link" => array(
          "from" => "unique_id_23",
          "to" => "unique_id_12"
        )
      ),
      array(
        "id" => "unique_id_link_11",
        "link" => array(
          "from" => "unique_id_13",
          "to" => "unique_id_12"
        )
      )
    ),
    "float" => array(
      array(
        "id" => "unique_id_float_1",
        "text" => "Eliminar o<br>desperdício de uso",
        "circleStrokeFill" => "#00FF00",
        "stroke" => "#AAAA00",
        "circleStroke" => "#AAAA00",
        "fill" => "#FFFF00",
        "x" => 10,
        "y" => 10
      )
    ),
    "data" => array(
      array(
        "id" => "unique_id_1",
        "text" => "Financeira",
        "fill" => "#FFFF00",
        "fontColor" => "#3498DB",
        "objective" => array(
          array(
            array(
              "id" => "unique_id_2",
              "text" => "Eliminar o<br>desperdício de uso",
              "circleStrokeFill" => "#00FF00",
              "stroke" => "#AAAA00",
              "circleStroke" => "#AAAA00",
              "fill" => "#FFFF00"
            ),
            array(
              "id" => "unique_id_3",
              "text" => "Aumentar a rentabilidade da<br>instituição de forma sustentável",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#AA0000",
              "circleStroke" => "#AAAA00",
              "fill" => "#FFFF00"
            ),
            array(
              "id" => "unique_id_4",
              "text" => "Aumentar a receita de<br>forma diversificada",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#AA0000",
              "circleStroke" => "#AAAA00",
              "fill" => "#FFFF00"
            )
          )
        )
      ),
      array(
        "id" => "unique_id_10",
        "text" => "Mercado e Cliente",
        "fill" => "#2C3E50",
        "fontColor" => "#FFFFFF",
        "objective" => array(
          array(
            array(
              "id" => "unique_id_11",
              "text" => "Desenvolver a satisfação dos pacientes,<br>Estado, Município e Operadoras",
              "circleStrokeFill" => "#FFFF00",
              "fontColor" => "#FFFFFF",
              "stroke" => "#0000FF"
            ),
            array(
              "id" => "unique_id_12",
              "text" => "Apresentar uma imagem de<br>resolutividade para os problemas",
              "circleStrokeFill" => "#FF0000",
              "fontColor" => "#FFFFFF",
              "stroke" => "#0000FF"
            ),
            array(
              "id" => "unique_id_13",
              "text" => "Fidelizar o corpo clínico da instituição",
              "circleStrokeFill" => "#FF0000",
              "fontColor" => "#FFFFFF",
              "stroke" => "#FF0000"
            )
          )
        )
      ),
      array(
        "id" => "unique_id_19",
        "text" => "Processos internos",
        "fill" => "#FF7777",
        "fontColor" => "#FFFFFF",
        "columns" => array(
          array(
            "id" => "unique_id_col_1",
            "text" => "Gestão de mercado/cliente",
            "fill" => "#FF7777",
            "fontColor" => "#FFFFFF"
          ),
          array(
            "id" => "unique_id_col_2",
            "text" => "Pesquisa e Inovação",
            "fill" => "#FF7777",
            "fontColor" => "#FFFFFF"
          ),
          array(
            "id" => "unique_id_col_3",
            "text" => "Excelência Operacional",
            "fill" => "#FF7777",
            "fontColor" => "#FFFFFF"
          ),
          array(
            "id" => "unique_id_col_4",
            "text" => "Desenvolvimento social",
            "fill" => "#FF7777",
            "fontColor" => "#FFFFFF"
          )
        ),
        "objective" => array(
          array(
            //Gestão de mercado/cliente
            array(
              "id" => "unique_id_21",
              "text" => "Desenvolver atendimento<br>humanizado no corpo",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            //Pesquisa e Inovação
            array(
              "id" => "unique_id_23",
              "text" => "Incentivar o<br>desenvolvimento de novos",
              "circleStrokeFill" => "#FFFF00",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            //Excelência Operacional
            array(
              "id" => "unique_id_20",
              "text" => "Desenvolver a qualidade<br>de atendimento acima dos<br>padrões do mercado.",
              "circleStrokeFill" => "#FFFF00",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            //Desenvolvimento social
            array(
              "id" => "unique_id_22",
              "text" => "Aumentar número de<br>horas dedicadas a<br>projetos",
              "circleStrokeFill" => "#00FF00",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            )
          ),
          array(
            //Gestão de mercado/cliente
            array(
              "id" => "unique_id_25",
              "text" => "Criar estruturas para atuar<br>também nos segmentos<br>de camada social",
              "circleStrokeFill" => "#FFFF00",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            //Pesquisa e Inovação
            array(
              "id" => "unique_id_27",
              "text" => "Aumentar o número<br>de parcerias e<br>projetos com faculdades",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            //Excelência Operacional
            array(
              "id" => "unique_id_24",
              "text" => "Desenvolver a qualidade<br>da instituição de forma<br>continua para garantir<br>certificações adquiridas",
              "circleStrokeFill" => "#FFFF00",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            //Desenvolvimento social
            array(
              "id" => "unique_id_26",
              "text" => "Compartilhar a excelência<br>científica e em gestão com<br>instituições filantrópicas<br>da mesma área",
              "circleStrokeFill" => "#00FF00",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
          ),
          array(
            array(),
            //Gestão de mercado/cliente
            array(
              "id" => "unique_id_28",
              "text" => "Criar estreitamento<br>no relacionamento<br>com as...",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            ),
            array(),
            //Pesquisa e Inovação
            array(
              "id" => "unique_id_29",
              "text" => "Estimular a criação<br>de trabalhos científicos",
              "circleStrokeFill" => "#999999",
              "stroke" => "#FF0000",
              "fill" => "#FF7777",
              "fontColor" => "#FFFFFF"
            )
          )
        )
      ),
      array(
        "id" => "unique_id_31",
        "text" => "Aprendizado e Crescimento",
        "fill" => "#F781F3",
        "fontColor" => "#FFFFFF",
        "columns" => array(
          array(
            "id" => "unique_id_col_5",
            "text" => "Desenvolver o capital humano",
            "fill" => "#F781F3",
            "fontColor" => "#FFFFFF"
          ),
          array(
            "id" => "unique_id_col_6",
            "text" => "Capital organizacional",
            "fill" => "#F781F3",
            "fontColor" => "#FFFFFF"
          ),
          array(
            "id" => "unique_id_col_7",
            "text" => "Capital da organização",
            "fill" => "#F781F3",
            "fontColor" => "#FFFFFF"
          )
        ),
        "objective" => array(
          array(
            array(
              "id" => "unique_id_32",
              "text" => "Desenvolver a<br>motivação e inovação",
              "circleStrokeFill" => "#FFFF00",
              "stroke" => "#8904B1",
              "fill" => "#F781F3",
              "fontColor" => "#FFFFFF"
            ),
            array(
              "id" => "unique_id_33",
              "text" => "Desenvolver um clima<br>organizacional mais adequado",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#FF0000",
              "fill" => "#F781F3",
              "fontColor" => "#FFFFFF"
            ),
            array(
              "id" => "unique_id_34",
              "text" => "Alimentar e integrar as<br>informações para ajudar a ...",
              "circleStrokeFill" => "#FF0000",
              "stroke" => "#FF0000",
              "fill" => "#F781F3",
              "fontColor" => "#FFFFFF"
            )
          ),
          array(
            array(
              "id" => "unique_id_35",
              "text" => "Criar cultura<br>humanizante no corpo",
              "circleStrokeFill" => "#FFFF00",
              "stroke" => "#FF0000",
              "fill" => "#F781F3",
              "fontColor" => "#FFFFFF"
            )
          )
        )
      )
    )
  );

  $fontSizeDefaultLUInt = 12;
  $spaceWidthBetweenTextAndBorderUInt = 50;
  $spaceHeightBetweenTextAndBorder = 10;
  $setup = array(
    "fontFamily" => "./tahoma.ttf",
    "perspectiveFontSizeDefault" => $fontSizeDefaultLUInt,
    "perspectiveFontColorDefault" => "#555555",
    "perspectiveStrokeDefaultColor" => "#000000",
    "perspectiveFillDefaultColor" => "#DDDDDD",
    "perspectiveStrokeWidth" => 0,
    "perspectiveRx" => 1,
    "perspectiveRy" => 1,
    "perspectiveCircleCx" => 7,
    "perspectiveCircleCy" => 7,
    "perspectiveCircleCR" => 7,
    "perspectiveCircleStroke" => "#000000",
    "perspectiveCircleStrokeWidth" => 2,
    "perspectiveCircleStrokeFill" => "#00FF00",
    "perspectiveSpaceWidthBetweenTextAndBorder" => $spaceWidthBetweenTextAndBorderUInt - 10,
    "perspectiveSpaceHeightBetweenTextAndBorder" => $spaceHeightBetweenTextAndBorder - 10,
    "perspectiveSpaceUpper" => 20,
    "perspectiveSpaceBottom" => 10,

    "columnsFontSizeDefault" => $fontSizeDefaultLUInt,
    "columnsFontColorDefault" => "#5555FF",
    "columnsStrokeDefaultColor" => "#000000",
    "columnsFillDefaultColor" => "#DDDDDD",
    "columnsStrokeWidth" => 0,
    "columnsRx" => 1,
    "columnsRy" => 1,
    "columnsCircleCx" => 7,
    "columnsCircleCy" => 7,
    "columnsCircleCR" => 7,
    "columnsCircleStroke" => "#000000",
    "columnsCircleStrokeWidth" => 2,
    "columnsCircleStrokeFill" => "#FFFF00",
    "columnsSpaceWidthBetweenTextAndBorder" => $spaceWidthBetweenTextAndBorderUInt - 10,
    "columnsSpaceHeightBetweenTextAndBorder" => $spaceHeightBetweenTextAndBorder - 10,
    "columnsSpaceWidthBetween" => 30,
    "columnsSpaceBottom" => 10,

    "objectivesFontSizeDefault" => $fontSizeDefaultLUInt,
    "objectivesFontColorDefault" => "#3498DB",
    "objectivesStrokeDefaultColor" => "#000000",
    "objectivesFillDefaultColor" => "#2C3E50",
    "objectivesStrokeWidth" => 2,
    "objectivesRx" => 1,
    "objectivesRy" => 1,
    "objectivesCircleCx" => 7,
    "objectivesCircleCy" => 7,
    "objectivesCircleCR" => 7,
    "objectivesCircleStroke" => "#000000",
    "objectivesCircleStrokeWidth" => 2,
    "objectivesCircleStrokeFill" => "#00FF00",
    "objectivesSpaceWidthBetween" => 30,
    "objectivesSpaceHeightBetween" => 20,
    "objectivesSpaceWidthBetweenTextAndBorder" => $spaceWidthBetweenTextAndBorderUInt,
    "objectivesSpaceHeightBetweenTextAndBorder" => $spaceHeightBetweenTextAndBorder

  );

  /*********************************************************************************************************************
   * Código PHP a ser copiado e colado - início
   ********************************************************************************************************************/
  $listElementsToAddLArr = array();
  $listLinksIdsLArr = array();

  /** [ public ] função principal encarregada de montar o código fonte.
   *
   * @param $dataAArr Array com os dados do gráfico.
   * @param $setupAArr Array com as configurações padrão do gráfico.
   * @param $listElementsToAddAArr Array em branco, usado como apoio.
   * @param $listLinksIdsAArr Array em branco, usado como apoio.
   * @code
  $(document).ready( function(){ <?php print makeOnReadyFunction( $data, $setup, $listElementsToAddLArr, $listLinksIdsLArr ); ?> });
   * @endcode
   * @return string
   */
  function makeOnReadyFunction( &$dataAArr, &$setupAArr, &$listElementsToAddAArr, &$listLinksIdsAArr ){
    $returnLStr = "
          var graph = new joint.dia.Graph();

          var paper = new joint.dia.Paper({
            el: $('#paper'),
            width: 5000,
            height: 5000,
            gridSize: 10,
            model: graph
          });

          joint.shapes.basic.Rect = joint.shapes.basic.Generic.extend({
            markup: '<g class=\"rotatable\"><g class=\"scalable\"><rect/></g><text/><svg height=\"90\" width=\"200\"><circle cx=\"7\" cy=\"7\" r=\"7\" stroke=\"black\" stroke-width=\"2\" fill=\"red\" /></svg></g>',
            defaults: joint.util.deepSupplement({
              type: 'basic.Rect',
              attrs: {
                'rect': { fill: 'white', stroke: 'black', 'follow-scale': true, width: 80, height: 40 },
                'text': { 'font-size': 14, 'ref-x': .5, 'ref-y': .5, ref: 'rect', 'y-alignment': 'middle', 'x-alignment': 'middle' }
              }
            }, joint.shapes.basic.Generic.prototype.defaults)
          });

         ". makeBalloons( 50, 150, $dataAArr, $setupAArr, $listElementsToAddAArr ). "
         ". makeLinks( $dataAArr, $listElementsToAddAArr, $listLinksIdsAArr ). "
          graph.addCells([ ". getListToAdd( $listElementsToAddAArr ) ." ]);
          var listUpdate = [ ". getListToAdd( $listElementsToAddAArr ) . " ];

          graph.on('change:position', function(cell) {\r\n";

    // has an obstacle been moved? Then reroute the link.
    foreach( $listLinksIdsAArr as $linkIdLStr ){
      $returnLStr .= "if (_.contains(listUpdate, cell)) paper.findViewByModel(".$linkIdLStr.").update();\r\n";
    }

    $returnLStr .= "
          });

          $('.router-switch').on('click', function(evt) {
            var router = $(evt.target).data('router');
            var connector = $(evt.target).data('connector');

            if (router) {
              link.set('router', { name: router });
            } else {
              link.unset('router');
            }

            link.set('connector', { name: connector });
          });
        ";

    return $returnLStr;
  }

  /** [ private ] Monta parte do código fonte do gráfico.
   *
   * @param $xAUInt Int com o posição x do gráfico.
   * @param $yAUInt Int com o posição y do gráfico.
   * @param $dataAArr Array com os dados do gráfico.
   * @param $setupAArr Array com as configurações padrão do gráfico.
   * @param $listElementsToAddLArr Array em branco, usado como apoio.
   *
   * @return string código fonte.
   */
  function makeBalloons( $xAUInt, $yAUInt, &$dataAArr, &$setupAArr, &$listElementsToAddLArr ){
    $returnLStr = "";
    $borderHeightSFlt = 0;

    $balloonWidthMaxUFlt = 0;

    $xColumnsLArr = array();

    if( @is_array( $dataAArr["float"] ) )
    {
      foreach($dataAArr["float"] as $perspectiveKeyLUInt => $perspectiveDataLArr)
      {

        /*****************************************************************************************************************
         * Balão de perspectivas.
         ****************************************************************************************************************/
        if(isset($perspectiveDataLArr["stroke"]))
        {
          $strokeColorLStr = $perspectiveDataLArr["stroke"];
        }
        else
        {
          $strokeColorLStr = $setupAArr["perspectiveStrokeDefaultColor"];
        }

        if(isset($perspectiveDataLArr["fill"]))
        {
          $perspectiveFillColorLStr = $perspectiveDataLArr["fill"];
        }
        else
        {
          $perspectiveFillColorLStr = $setupAArr["perspectiveFillDefaultColor"];
        }

        if(isset($perspectiveDataLArr["strokeWidth"]))
        {
          $strokeWidthLUInt = $perspectiveDataLArr["strokeWidth"];
        }
        else
        {
          $strokeWidthLUInt = $setupAArr["perspectiveStrokeWidth"];
        }

        if(isset($perspectiveDataLArr["rx"]))
        {
          $perspectiveRxLUFlt = $perspectiveDataLArr["rx"];
        }
        else
        {
          $perspectiveRxLUFlt = $setupAArr["perspectiveRx"];
        }

        if(isset($perspectiveDataLArr["ry"]))
        {
          $perspectiveRyLUFlt = $perspectiveDataLArr["ry"];
        }
        else
        {
          $perspectiveRyLUFlt = $setupAArr["perspectiveRy"];
        }

        if(isset($perspectiveDataLArr["fontSize"]))
        {
          $perspectiveFontSizeUInt = $perspectiveDataLArr["fontSize"];
        }
        else
        {
          $perspectiveFontSizeUInt = $setupAArr["perspectiveFontSizeDefault"];
        }

        if(isset($perspectiveDataLArr["fontColor"]))
        {
          $perspectiveFontColorLStr = $perspectiveDataLArr["fontColor"];
        }
        else
        {
          $perspectiveFontColorLStr = $setupAArr["perspectiveFontColorDefault"];
        }

        if(isset($perspectiveDataLArr["circleCx"]))
        {
          $perspectiveCircleCxUFlt = $perspectiveDataLArr["circleCx"];
        }
        else
        {
          $perspectiveCircleCxUFlt = $setupAArr["perspectiveCircleCx"];
        }

        if(isset($perspectiveDataLArr["circleCy"]))
        {
          $perspectiveCircleCyUFlt = $perspectiveDataLArr["circleCy"];
        }
        else
        {
          $perspectiveCircleCyUFlt = $setupAArr["perspectiveCircleCy"];
        }

        if(isset($perspectiveDataLArr["circleCR"]))
        {
          $perspectiveCircleCrUFlt = $perspectiveDataLArr["circleCR"];
        }
        else
        {
          $perspectiveCircleCrUFlt = $setupAArr["perspectiveCircleCR"];
        }

        if(isset($perspectiveDataLArr["circleStroke"]))
        {
          $perspectiveCircleStrokeUFlt = $perspectiveDataLArr["circleStroke"];
        }
        else
        {
          $perspectiveCircleStrokeUFlt = $setupAArr["perspectiveCircleStroke"];
        }

        if(isset($perspectiveDataLArr["circleStrokeWidth"]))
        {
          $perspectiveCircleStrokeWidthUFlt = $perspectiveDataLArr["circleStrokeWidth"];
        }
        else
        {
          $perspectiveCircleStrokeWidthUFlt = $setupAArr["perspectiveCircleStrokeWidth"];
        }

        if(isset($perspectiveDataLArr["circleStrokeFill"]))
        {
          $perspectiveCircleStrokeFillUFlt = $perspectiveDataLArr["circleStrokeFill"];
        }
        else
        {
          $perspectiveCircleStrokeFillUFlt = $setupAArr["perspectiveCircleStrokeFill"];
        }

        $listElementsToAddLArr[] = $perspectiveDataLArr["id"];

        $returnLStr .= "        ";
        $returnLStr .= "joint.shapes.basic.Rect = joint.shapes.basic.Generic.extend({
            markup: '<g class=\'rotatable\'><g class=\'scalable\'><rect/></g><text/><!--svg height=\'90\' width=\'100\'><circle cx=\'" . $perspectiveCircleCxUFlt . "\' cy=\'" . $perspectiveCircleCyUFlt . "\' r=\'" . $perspectiveCircleCrUFlt . "\' stroke=\'" . $perspectiveCircleStrokeUFlt . "\' stroke-width=\'" . $perspectiveCircleStrokeWidthUFlt . "\' fill=\'" . $perspectiveCircleStrokeFillUFlt . "\' /></svg--></g>',
            defaults: joint.util.deepSupplement({
              type: 'basic.Rect',
              attrs: {
                'rect': { fill: 'white', stroke: 'black', 'follow-scale': true, width: 80, height: 40 },
                'text': { 'font-size': 14, 'ref-x': .5, 'ref-y': .5, ref: 'rect', 'y-alignment': 'middle', 'x-alignment': 'middle' }
              }
            }, joint.shapes.basic.Generic.prototype.defaults)
          });\r\n";
        $returnLStr .= "        ";
        $returnLStr .= "var " . $perspectiveDataLArr["id"] . " = new joint.shapes.basic.Rect({
        position : {
          x : " . $perspectiveDataLArr["x"] . ",
          y : " . $perspectiveDataLArr["y"] . "
        },
        size : {
          width : " . (getWidthTextSize($perspectiveDataLArr["text"], $setupAArr["fontFamily"], $perspectiveFontSizeUInt) + 2 * $setupAArr["perspectiveSpaceWidthBetweenTextAndBorder"]) . ",
          height : " . (getHeightTextSize($perspectiveDataLArr["text"], $setupAArr["fontFamily"], $perspectiveFontSizeUInt) + 2 * $setupAArr["perspectiveSpaceHeightBetweenTextAndBorder"]) . "
        },
        attrs : {
          rect: { fill: '" . $perspectiveFillColorLStr . "', rx: " . $perspectiveRxLUFlt . ", ry: " . $perspectiveRyLUFlt . ", 'stroke-width': " . $strokeWidthLUInt . ", stroke: '" . $strokeColorLStr . "' },
          text: {
            text: '" . transformText($perspectiveDataLArr["text"]) . "',
            fill: '" . $perspectiveFontColorLStr . "',
            'font-size': " . $perspectiveFontSizeUInt . ",
            'ref-y':.5
          }
        }
      });\r\n";
      }
    }

    foreach( $dataAArr["data"] as $perspectiveKeyLUInt => $perspectiveDataLArr ){

      /*****************************************************************************************************************
       * Balão de rotulos de colunas.
       ****************************************************************************************************************/
      if( @is_array( $perspectiveDataLArr[ "columns" ] ) ){
        foreach( $perspectiveDataLArr[ "columns" ] as $objectiveKeyLArr => $objectiveLArr ){
          if( isset( $objectiveLArr["fontSize"] ) ){
            $columnsFontSizeUInt = $objectiveLArr["fontSize"];
          }
          else{
            $columnsFontSizeUInt = $setupAArr["columnsFontSizeDefault"];
          }

          if( isset( $objectiveLArr["id"] ) ){
            $balloonWidthMaxUFlt = max( $balloonWidthMaxUFlt, getWidthTextSize($objectiveLArr["text"], $setupAArr["fontFamily"], $columnsFontSizeUInt) );
          }
        }
      }

      /*****************************************************************************************************************
       * Balão de objetivos.
       ****************************************************************************************************************/

      $borderWidthSFlt = 0;

      foreach( $perspectiveDataLArr[ "objective" ] as $objectiveKeyLUInt => $objectiveListLArr ){
        foreach( $objectiveListLArr as $objectiveBalloonKeyUInt => $objectiveBalloonValuesLArr ){
          if( $objectiveBalloonKeyUInt == 0 ){
            $borderWidthSFlt = $xAUInt;
          }
          else{
            $borderWidthSFlt += $setupAArr["objectivesSpaceWidthBetween"];
          }

          if( isset( $objectiveBalloonValuesLArr["fontSize"] ) ){
            $objectivesFontSizeUInt = $objectiveBalloonValuesLArr["fontSize"];
          }
          else{
            $objectivesFontSizeUInt = $setupAArr["objectivesFontSizeDefault"];
          }

          if( isset( $objectiveBalloonValuesLArr["id"] ) ){
            $balloonWidthMaxUFlt = max( $balloonWidthMaxUFlt, getWidthTextSize($objectiveBalloonValuesLArr["text"], $setupAArr["fontFamily"], $objectivesFontSizeUInt) );
          }
        }
      }
    }

    // Monta o x de cada balão

    $borderWidthSFlt = 0;

    foreach( $dataAArr["data"] as $perspectiveKeyLUInt => $perspectiveDataLArr ){

      foreach( $perspectiveDataLArr[ "objective" ] as $objectiveKeyLUInt => $objectiveListLArr ){
        foreach( $objectiveListLArr as $objectiveBalloonKeyUInt => $objectiveBalloonValuesLArr ){
          if( $objectiveBalloonKeyUInt == 0 ){
            $borderWidthSFlt = $xAUInt;
          }
          else{
            $borderWidthSFlt += $setupAArr["objectivesSpaceWidthBetween"];
          }

          $xColumnsLArr[$objectiveBalloonKeyUInt] = $borderWidthSFlt;

          $borderWidthSFlt += $balloonWidthMaxUFlt + $setupAArr["objectivesSpaceWidthBetween"] + 2 * $setupAArr["objectivesSpaceWidthBetweenTextAndBorder"];
        }
      }
    }

    foreach( $dataAArr["data"] as $perspectiveKeyLUInt => $perspectiveDataLArr ){

      /*****************************************************************************************************************
       * Balão de perspectivas.
       ****************************************************************************************************************/
      if( $perspectiveKeyLUInt == 0 ){
        $borderHeightSFlt = $yAUInt;
        $_borderHSFlt = $borderHeightSFlt;
      }
      else{
        $_borderHSFlt = $borderHeightSFlt + $setupAArr["perspectiveSpaceUpper"];
      }

      if( isset( $perspectiveDataLArr["stroke"] ) ){
        $strokeColorLStr = $perspectiveDataLArr["stroke"];
      }
      else{
        $strokeColorLStr = $setupAArr["perspectiveStrokeDefaultColor"];
      }

      if( isset( $perspectiveDataLArr["fill"] ) ){
        $perspectiveFillColorLStr = $perspectiveDataLArr["fill"];
      }
      else{
        $perspectiveFillColorLStr = $setupAArr["perspectiveFillDefaultColor"];
      }

      if( isset( $perspectiveDataLArr["strokeWidth"] ) ){
        $strokeWidthLUInt = $perspectiveDataLArr["strokeWidth"];
      }
      else{
        $strokeWidthLUInt = $setupAArr["perspectiveStrokeWidth"];
      }

      if( isset( $perspectiveDataLArr["rx"] ) )
      {
        $perspectiveRxLUFlt = $perspectiveDataLArr["rx"];
      }
      else{
        $perspectiveRxLUFlt = $setupAArr["perspectiveRx"];
      }

      if( isset( $perspectiveDataLArr["ry"] ) )
      {
        $perspectiveRyLUFlt = $perspectiveDataLArr["ry"];
      }
      else{
        $perspectiveRyLUFlt = $setupAArr["perspectiveRy"];
      }

      if( isset( $perspectiveDataLArr["fontSize"] ) ){
        $perspectiveFontSizeUInt = $perspectiveDataLArr["fontSize"];
      }
      else{
        $perspectiveFontSizeUInt = $setupAArr["perspectiveFontSizeDefault"];
      }

      if( isset( $perspectiveDataLArr["fontColor"] ) ){
        $perspectiveFontColorLStr = $perspectiveDataLArr["fontColor"];
      }
      else{
        $perspectiveFontColorLStr = $setupAArr["perspectiveFontColorDefault"];
      }

      if( isset( $perspectiveDataLArr["circleCx"] ) ){
        $perspectiveCircleCxUFlt = $perspectiveDataLArr["circleCx"];
      }
      else{
        $perspectiveCircleCxUFlt = $setupAArr["perspectiveCircleCx"];
      }

      if( isset( $perspectiveDataLArr["circleCy"] ) ){
        $perspectiveCircleCyUFlt = $perspectiveDataLArr["circleCy"];
      }
      else{
        $perspectiveCircleCyUFlt = $setupAArr["perspectiveCircleCy"];
      }

      if( isset( $perspectiveDataLArr["circleCR"] ) ){
        $perspectiveCircleCrUFlt = $perspectiveDataLArr["circleCR"];
      }
      else{
        $perspectiveCircleCrUFlt = $setupAArr["perspectiveCircleCR"];
      }

      if( isset( $perspectiveDataLArr["circleStroke"] ) ){
        $perspectiveCircleStrokeUFlt = $perspectiveDataLArr["circleStroke"];
      }
      else{
        $perspectiveCircleStrokeUFlt = $setupAArr["perspectiveCircleStroke"];
      }

      if( isset( $perspectiveDataLArr["circleStrokeWidth"] ) ){
        $perspectiveCircleStrokeWidthUFlt = $perspectiveDataLArr["circleStrokeWidth"];
      }
      else{
        $perspectiveCircleStrokeWidthUFlt = $setupAArr["perspectiveCircleStrokeWidth"];
      }

      if( isset( $perspectiveDataLArr["circleStrokeFill"] ) ){
        $perspectiveCircleStrokeFillUFlt = $perspectiveDataLArr["circleStrokeFill"];
      }
      else{
        $perspectiveCircleStrokeFillUFlt = $setupAArr["perspectiveCircleStrokeFill"];
      }

      $listElementsToAddLArr[] = $perspectiveDataLArr["id"];

      $returnLStr .= "        ";
      $returnLStr .= "joint.shapes.basic.Rect = joint.shapes.basic.Generic.extend({
            markup: '<g class=\'rotatable\'><g class=\'scalable\'><rect/></g><text/><!--svg height=\'90\' width=\'100\'><circle cx=\'" . $perspectiveCircleCxUFlt . "\' cy=\'" . $perspectiveCircleCyUFlt . "\' r=\'" . $perspectiveCircleCrUFlt . "\' stroke=\'" . $perspectiveCircleStrokeUFlt . "\' stroke-width=\'" . $perspectiveCircleStrokeWidthUFlt . "\' fill=\'" . $perspectiveCircleStrokeFillUFlt . "\' /></svg--></g>',
            defaults: joint.util.deepSupplement({
              type: 'basic.Rect',
              attrs: {
                'rect': { fill: 'white', stroke: 'black', 'follow-scale': true, width: 80, height: 40 },
                'text': { 'font-size': 14, 'ref-x': .5, 'ref-y': .5, ref: 'rect', 'y-alignment': 'middle', 'x-alignment': 'middle' }
              }
            }, joint.shapes.basic.Generic.prototype.defaults)
          });\r\n";
      $returnLStr .= "        ";
      $returnLStr .= "var " . $perspectiveDataLArr["id"] . " = new joint.shapes.basic.Rect({
        position : {
          x : " . $xAUInt . ",
          y : " . $_borderHSFlt . "
        },
        size : {
          width : " . ( getWidthTextSize($perspectiveDataLArr["text"], $setupAArr["fontFamily"], $perspectiveFontSizeUInt) + 2 * $setupAArr["perspectiveSpaceWidthBetweenTextAndBorder"] ) . ",
          height : " . ( getHeightTextSize($perspectiveDataLArr["text"], $setupAArr["fontFamily"], $perspectiveFontSizeUInt) + 2 * $setupAArr["perspectiveSpaceHeightBetweenTextAndBorder"] ) . "
        },
        attrs : {
          rect: { fill: '" . $perspectiveFillColorLStr . "', rx: " . $perspectiveRxLUFlt . ", ry: " . $perspectiveRyLUFlt . ", 'stroke-width': " . $strokeWidthLUInt . ", stroke: '" . $strokeColorLStr . "' },
          text: {
            text: '" . transformText($perspectiveDataLArr["text"]) . "',
            fill: '" . $perspectiveFontColorLStr . "',
            'font-size': " . $perspectiveFontSizeUInt . ",
            'ref-y':.5
          }
        }
      });\r\n";

      if( $perspectiveKeyLUInt == 0 ){
        $borderHeightSFlt += getHeightTextSize($perspectiveDataLArr["text"], $setupAArr["fontFamily"], $perspectiveFontSizeUInt) + $setupAArr[ "perspectiveSpaceBottom" ] + 2 * $setupAArr["perspectiveSpaceHeightBetweenTextAndBorder"];
      }
      else{
        $borderHeightSFlt += getHeightTextSize($perspectiveDataLArr["text"], $setupAArr["fontFamily"], $perspectiveFontSizeUInt) + $setupAArr[ "perspectiveSpaceBottom" ] + $setupAArr["perspectiveSpaceUpper"] + 2 * $setupAArr["perspectiveSpaceHeightBetweenTextAndBorder"];
      }

      /*****************************************************************************************************************
       * Balão de rotulos de colunas.
       ****************************************************************************************************************/
      if( @is_array( $perspectiveDataLArr[ "columns" ] ) ){
        $borderHMaxSFlt = 0;
        $borderWidthSFlt = $xAUInt;

        foreach( $perspectiveDataLArr[ "columns" ] as $objectiveKeyLArr => $objectiveLArr ){
          if( !isset( $objectiveLArr["id"] ) ){
            continue;
          }

          if( isset( $objectiveLArr["stroke"] ) ){
            $strokeColorLStr = $objectiveLArr["stroke"];
          }
          else{
            $strokeColorLStr = $setupAArr["columnsStrokeDefaultColor"];
          }

          if( isset( $objectiveLArr["fill"] ) ){
            $columnsFillColorLStr = $objectiveLArr["fill"];
          }
          else{
            $columnsFillColorLStr = $setupAArr["columnsFillDefaultColor"];
          }

          if( isset( $objectiveLArr["strokeWidth"] ) ){
            $strokeWidthLUInt = $objectiveLArr["strokeWidth"];
          }
          else{
            $strokeWidthLUInt = $setupAArr["columnsStrokeWidth"];
          }

          if( isset( $objectiveLArr["rx"] ) )
          {
            $columnsRxLUFlt = $objectiveLArr["rx"];
          }
          else{
            $columnsRxLUFlt = $setupAArr["columnsRx"];
          }

          if( isset( $objectiveLArr["ry"] ) )
          {
            $columnsRyLUFlt = $objectiveLArr["ry"];
          }
          else{
            $columnsRyLUFlt = $setupAArr["columnsRy"];
          }

          if( isset( $objectiveLArr["fontSize"] ) ){
            $columnsFontSizeUInt = $objectiveLArr["fontSize"];
          }
          else{
            $columnsFontSizeUInt = $setupAArr["columnsFontSizeDefault"];
          }

          if( isset( $objectiveLArr["fontColor"] ) ){
            $columnsFontColorLStr = $objectiveLArr["fontColor"];
          }
          else{
            $columnsFontColorLStr = $setupAArr["columnsFontColorDefault"];
          }

          if( isset( $columnsDataLArr["circleCx"] ) ){
            $columnsCircleCxUFlt = $columnsDataLArr["circleCx"];
          }
          else{
            $columnsCircleCxUFlt = $setupAArr["columnsCircleCx"];
          }

          if( isset( $columnsDataLArr["circleCy"] ) ){
            $columnsCircleCyUFlt = $columnsDataLArr["circleCy"];
          }
          else{
            $columnsCircleCyUFlt = $setupAArr["columnsCircleCy"];
          }

          if( isset( $columnsDataLArr["circleCR"] ) ){
            $columnsCircleCrUFlt = $columnsDataLArr["circleCR"];
          }
          else{
            $columnsCircleCrUFlt = $setupAArr["columnsCircleCR"];
          }

          if( isset( $columnsDataLArr["circleStroke"] ) ){
            $columnsCircleStrokeUFlt = $columnsDataLArr["circleStroke"];
          }
          else{
            $columnsCircleStrokeUFlt = $setupAArr["columnsCircleStroke"];
          }

          if( isset( $columnsDataLArr["circleStrokeWidth"] ) ){
            $columnsCircleStrokeWidthUFlt = $columnsDataLArr["circleStrokeWidth"];
          }
          else{
            $columnsCircleStrokeWidthUFlt = $setupAArr["columnsCircleStrokeWidth"];
          }

          if( isset( $columnsDataLArr["circleStrokeFill"] ) ){
            $columnsCircleStrokeFillUFlt = $columnsDataLArr["circleStrokeFill"];
          }
          else{
            $columnsCircleStrokeFillUFlt = $setupAArr["columnsCircleStrokeFill"];
          }

          $listElementsToAddLArr[] = $objectiveLArr["id"];

          $returnLStr .= "        ";
          $returnLStr .= "joint.shapes.basic.Rect = joint.shapes.basic.Generic.extend({
            markup: '<g class=\'rotatable\'><g class=\'scalable\'><rect/></g><text/><!--svg height=\'90\' width=\'100\'><circle cx=\'" . $columnsCircleCxUFlt . "\' cy=\'" . $columnsCircleCyUFlt . "\' r=\'" . $columnsCircleCrUFlt . "\' stroke=\'" . $columnsCircleStrokeUFlt . "\' stroke-width=\'" . $columnsCircleStrokeWidthUFlt . "\' fill=\'" . $columnsCircleStrokeFillUFlt . "\' /></svg--></g>',
            defaults: joint.util.deepSupplement({
              type: 'basic.Rect',
              attrs: {
                'rect': { fill: 'white', stroke: 'black', 'follow-scale': true, width: 80, height: 40 },
                'text': { 'font-size': 14, 'ref-x': .5, 'ref-y': .5, ref: 'rect', 'y-alignment': 'middle', 'x-alignment': 'middle' }
              }
            }, joint.shapes.basic.Generic.prototype.defaults)
          });\r\n";
          $returnLStr .= "        ";
          $returnLStr .= "var " . $objectiveLArr["id"] . " = new joint.shapes.basic.Rect({
            position : {
              x : " . ($xColumnsLArr[$objectiveKeyLArr]) . ",
              y : " . $borderHeightSFlt . "
            },
            size : {
              width : " . ( getWidthTextSize($objectiveLArr["text"], $setupAArr["fontFamily"], $columnsFontSizeUInt) + 2 * $setupAArr["columnsSpaceWidthBetweenTextAndBorder"] ) . ",
              height : " . ( getHeightTextSize($objectiveLArr["text"], $setupAArr["fontFamily"], $columnsFontSizeUInt) + 2 * $setupAArr["columnsSpaceHeightBetweenTextAndBorder"] ) . "
            },
            attrs : {
              rect: { fill: '" . $columnsFillColorLStr . "', rx: " . $columnsRxLUFlt . ", ry: " . $columnsRyLUFlt . ", 'stroke-width': " . $strokeWidthLUInt . ", stroke: '" . $strokeColorLStr . "' },
              text: {
                text: '" . transformText($objectiveLArr["text"]) . "',
                fill: '" . $columnsFontColorLStr . "',
                'font-size': " . $columnsFontSizeUInt . ",
                'ref-y':.5
              }
            }
          });\r\n";

          $borderHMaxSFlt = max( $borderHMaxSFlt, getHeightTextSize($objectiveLArr["text"], $setupAArr["fontFamily"], $columnsFontSizeUInt) + $setupAArr["columnsSpaceBottom"] + 2 * $setupAArr["columnsSpaceHeightBetweenTextAndBorder"] );

          $borderWidthSFlt += $balloonWidthMaxUFlt + $setupAArr["objectivesSpaceWidthBetween"] + 2 * $setupAArr["objectivesSpaceWidthBetweenTextAndBorder"];
        }

        $borderHeightSFlt += $borderHMaxSFlt;
      }

      /*****************************************************************************************************************
       * Balão de objetivos.
       ****************************************************************************************************************/
      foreach( $perspectiveDataLArr[ "objective" ] as $objectiveKeyLUInt => $objectiveListLArr ){

        $borderWidthSFlt = $xAUInt;
        $borderHMaxSFlt = 0;

        foreach( $objectiveListLArr as $objectiveBalloonKeyUInt => $objectiveBalloonValuesLArr ){
          if( !isset( $objectiveBalloonValuesLArr["id"] ) ){
            continue;
          }

          if( $objectiveBalloonKeyUInt == 0 ){
            $borderWidthSFlt = $xAUInt;
          }
          else{
            $borderWidthSFlt += $setupAArr["objectivesSpaceWidthBetween"];
          }

          if( isset( $objectiveBalloonValuesLArr["stroke"] ) ){
            $strokeColorLStr = $objectiveBalloonValuesLArr["stroke"];
          }
          else{
            $strokeColorLStr = $setupAArr["objectivesStrokeDefaultColor"];
          }

          if( isset( $objectiveBalloonValuesLArr["fill"] ) ){
            $objectivesFillColorLStr = $objectiveBalloonValuesLArr["fill"];
          }
          else{
            $objectivesFillColorLStr = $setupAArr["objectivesFillDefaultColor"];
          }

          if( isset( $objectiveBalloonValuesLArr["strokeWidth"] ) ){
            $strokeWidthLUInt = $objectiveBalloonValuesLArr["strokeWidth"];
          }
          else{
            $strokeWidthLUInt = $setupAArr["objectivesStrokeWidth"];
          }

          if( isset( $objectiveBalloonValuesLArr["rx"] ) )
          {
            $objectivesRxLUFlt = $objectiveBalloonValuesLArr["rx"];
          }
          else{
            $objectivesRxLUFlt = $setupAArr["objectivesRx"];
          }

          if( isset( $objectiveBalloonValuesLArr["ry"] ) )
          {
            $objectivesRyLUFlt = $objectiveBalloonValuesLArr["ry"];
          }
          else{
            $objectivesRyLUFlt = $setupAArr["objectivesRy"];
          }

          if( isset( $objectiveBalloonValuesLArr["fontSize"] ) ){
            $objectivesFontSizeUInt = $objectiveBalloonValuesLArr["fontSize"];
          }
          else{
            $objectivesFontSizeUInt = $setupAArr["objectivesFontSizeDefault"];
          }

          if( isset( $objectiveBalloonValuesLArr["fontColor"] ) ){
            $objectivesFontColorLStr = $objectiveBalloonValuesLArr["fontColor"];
          }
          else{
            $objectivesFontColorLStr = $setupAArr["objectivesFontColorDefault"];
          }

          if( isset( $objectiveBalloonValuesLArr["circleCx"] ) ){
            $objectivesCircleCxUFlt = $objectiveBalloonValuesLArr["circleCx"];
          }
          else{
            $objectivesCircleCxUFlt = $setupAArr["objectivesCircleCx"];
          }

          if( isset( $objectiveBalloonValuesLArr["circleCy"] ) ){
            $objectivesCircleCyUFlt = $objectiveBalloonValuesLArr["circleCy"];
          }
          else{
            $objectivesCircleCyUFlt = $setupAArr["objectivesCircleCy"];
          }

          if( isset( $objectiveBalloonValuesLArr["circleCR"] ) ){
            $objectivesCircleCrUFlt = $objectiveBalloonValuesLArr["circleCR"];
          }
          else{
            $objectivesCircleCrUFlt = $setupAArr["objectivesCircleCR"];
          }

          if( isset( $objectiveBalloonValuesLArr["circleStroke"] ) ){
            $objectivesCircleStrokeUFlt = $objectiveBalloonValuesLArr["circleStroke"];
          }
          else{
            $objectivesCircleStrokeUFlt = $setupAArr["objectivesCircleStroke"];
          }

          if( isset( $objectiveBalloonValuesLArr["circleStrokeWidth"] ) ){
            $objectivesCircleStrokeWidthUFlt = $objectiveBalloonValuesLArr["circleStrokeWidth"];
          }
          else{
            $objectivesCircleStrokeWidthUFlt = $setupAArr["objectivesCircleStrokeWidth"];
          }

          if( isset( $objectiveBalloonValuesLArr["circleStrokeFill"] ) ){
            $objectivesCircleStrokeFillUFlt = $objectiveBalloonValuesLArr["circleStrokeFill"];
          }
          else{
            $objectivesCircleStrokeFillUFlt = $setupAArr["objectivesCircleStrokeFill"];
          }

          $listElementsToAddLArr[] = $objectiveBalloonValuesLArr["id"];

          $returnLStr .= "        ";
          $returnLStr .= "joint.shapes.basic.Rect = joint.shapes.basic.Generic.extend({
            markup: '<g class=\'rotatable\'><g class=\'scalable\'><rect/></g><text/><svg height=\'90\' width=\'100\'><circle cx=\'" . $objectivesCircleCxUFlt . "\' cy=\'" . $objectivesCircleCyUFlt . "\' r=\'" . $objectivesCircleCrUFlt . "\' stroke=\'" . $objectivesCircleStrokeUFlt . "\' stroke-width=\'" . $objectivesCircleStrokeWidthUFlt . "\' fill=\'" . $objectivesCircleStrokeFillUFlt . "\' /></svg></g>',
            defaults: joint.util.deepSupplement({
              type: 'basic.Rect',
              attrs: {
                'rect': { fill: 'white', stroke: 'black', 'follow-scale': true, width: 80, height: 40 },
                'text': { 'font-size': 14, 'ref-x': .5, 'ref-y': .5, ref: 'rect', 'y-alignment': 'middle', 'x-alignment': 'middle' }
              }
            }, joint.shapes.basic.Generic.prototype.defaults)
          });\r\n";
          $returnLStr .= "        ";
          $returnLStr .= "var " . $objectiveBalloonValuesLArr["id"] . " = new joint.shapes.basic.Rect({
            position : {
              x : " . ($xColumnsLArr[$objectiveBalloonKeyUInt]) . ",
              y : " . $borderHeightSFlt . "
            },
            size : {
              width : " . ( getWidthTextSize($objectiveBalloonValuesLArr["text"], $setupAArr["fontFamily"], $objectivesFontSizeUInt) + 2 * $setupAArr["objectivesSpaceWidthBetweenTextAndBorder"] ) . ",
              height : " . ( getHeightTextSize($objectiveBalloonValuesLArr["text"], $setupAArr["fontFamily"], $objectivesFontSizeUInt) + 2 * $setupAArr["objectivesSpaceHeightBetweenTextAndBorder"] ) . "
            },
            attrs : {
              rect: { fill: '" . $objectivesFillColorLStr . "', rx: " . $objectivesRxLUFlt . ", ry: " . $objectivesRyLUFlt . ", 'stroke-width': " . $strokeWidthLUInt . ", stroke: '" . $strokeColorLStr ."' },
              text: {
                text: '" . transformText($objectiveBalloonValuesLArr["text"]) . "',
                fill: '" . $objectivesFontColorLStr . "',
                'font-size': " . $objectivesFontSizeUInt . ",
                'ref-y':.5
              }
            }
          });\r\n";

          $borderHMaxSFlt = max( $borderHMaxSFlt, ( getHeightTextSize($objectiveBalloonValuesLArr["text"], $setupAArr["fontFamily"], $objectivesFontSizeUInt) + 2 * $setupAArr["objectivesSpaceHeightBetween"] + 2 * $setupAArr["objectivesSpaceHeightBetweenTextAndBorder"] ) );
          $borderWidthSFlt += $balloonWidthMaxUFlt + $setupAArr["objectivesSpaceWidthBetween"] + 2 * $setupAArr["objectivesSpaceWidthBetweenTextAndBorder"];
        }

        $borderHeightSFlt += $borderHMaxSFlt;
      }
    }

    return $returnLStr;
  }

  /** [ private ] Converte as quebras de linha html em \r\n.
   * @param $textAStr String com o texto original
   *
   * @return String com o texto pronto para ser inserido em funções JavaScript
   */
  function transformText( $textAStr ){
    $textAStr = preg_replace("/<br.*?>[\r\n]*/", "\\r\\n", $textAStr );
    return str_replace("'", "\\'", $textAStr );
  }

  /** [ private ] Retorna o tamanho horizontal do texto em pixels.
   *  [Não havia tempo e eu fui pela forma mais rapida.]
   * @param $textAStr String texto convertido para o formato JavaScript.
   * @param $fontFamilyAStr String com o caminho do arquivo da fonte.
   * @param $fontSizeAUInt Int com o tamanho da fonte.
   * @see transformText()
   *
   * @return Float com o tamanho do texto em pixels
   */
  function getWidthTextSize( &$textAStr, &$fontFamilyAStr, &$fontSizeAUInt ){
    $textLStr = preg_replace( "/<br.*?>[\r\n]*/", "\r\n", $textAStr );

    $charUInt = 0;
    $textInLinesLArr = explode( "\r\n", $textLStr );
    foreach( $textInLinesLArr as $lineLArr ){
      $charUInt = max( $charUInt, strlen( $lineLArr ) );
    }

    $fontDataLArr = imageftbbox ( $fontSizeAUInt, 0.0, $fontFamilyAStr, $textLStr );

    //O tamanho da fonte calculado pelo PHP não bate com o tamanho da fonte no navegador.
    return ( $fontDataLArr[ 2 ] - $fontDataLArr[ 0 ] ) - ( $charUInt * 2.5 );
  }

  /** [ private ] Retorna o tamanho horizontal do texto em pixels.
   *  [Não havia tempo e eu fui pela forma mais rapida.]
   * @param $textAStr String texto convertido para o formato JavaScript.
   * @param $fontFamilyAStr String com o caminho do arquivo da fonte.
   * @param $fontSizeAUInt Int com o tamanho da fonte.
   * @see transformText()
   *
   * @return Float com o tamanho do texto em pixels
   */
  function getHeightTextSize( &$textAStr, &$fontFamilyAStr, &$fontSizeAUInt ){
    $textLStr = preg_replace( "/<br.*?>[\r\n]*/", "\r\n", $textAStr );
    preg_match_all( "%([\r\n]+)%si", $textLStr, $matchesArr );
    $fontDataLArr = imageftbbox ( $fontSizeAUInt, 0.0, $fontFamilyAStr, $textLStr );

    //O tamanho da fonte calculado pelo PHP não bate com o tamanho da fonte no navegador.
    return ( $fontDataLArr[ 1 ] - $fontDataLArr[ 7 ] ) - ( ( count($matchesArr[0]) - 1 ) * 12 );
  }

  /** [ private ] Retorna a lista com todos os ids/nomes de variáveis geradas pelo código.
   *
   * @param $listElementsToAddLArr
   *
   * @return string com todos os nomes de variáveis separados por vírgula.
   */
  function getListToAdd( &$listElementsToAddLArr ){
    return implode( ", ", $listElementsToAddLArr );
  }

  /** [ private ] monta o código referente aos links
   * @param $dataAArr
   * @param $listElementsToAddAArr
   * @param $listLinksIdsAArr
   *
   * @return string
   */
  function makeLinks( &$dataAArr, &$listElementsToAddAArr, &$listLinksIdsAArr ){
    $returnLStr  = "";

    foreach( $dataAArr["link"] as $linkKeyUInt => $linkValueLArr )
    {
      $listElementsToAddAArr[] = $linkValueLArr["id"];
      $listLinksIdsAArr[] = $linkValueLArr["id"];

      $returnLStr .= "";
      $returnLStr .= "var " . $linkValueLArr["id"] . " = new joint.dia.Link({
        source: { id: " . $linkValueLArr["link"]["from"] . ".id },
        target: { id: " . $linkValueLArr["link"]["to"] . ".id },
        router: { name: 'manhattan' },
        connector: { name: 'rounded' },
        attrs: {
          '.connection': {
            stroke: '#333333',
            'stroke-width': 3
          },
          '.marker-target': {
            fill: '#333333',
            d: 'M 10 0 L 0 5 L 10 10 z'
          }
        }
      });\r\n";
    }

    return $returnLStr;
  }
  /*********************************************************************************************************************
   * Código PHP a ser copiado e colado - fim
   ********************************************************************************************************************/
?><html>
  <head>
    <link rel="stylesheet" type="text/css" href="./css/dev/joint.css" />
    <script src="./js/jquery.min.js"></script>
    <script src="./js/lodash.min.js"></script>
    <script src="./js/backbone-min.js"></script>
    <script src="./js/dev/joint.js"></script>
    <script>
      $(document).ready(
        function() {
          <?php print makeOnReadyFunction( $data, $setup, $listElementsToAddLArr, $listLinksIdsLArr ); ?>
        });
    </script>
  </head>
  <body>
    <dic id='paper' />
  </body>
</html>
```
