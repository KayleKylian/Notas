# Windows Presentation Foundation
WPF é uma estrutura de interface do usuário que é independente de resolução e usa um mecanismo de renderização baseado em vetor, criado para aproveitar o hardware gráfico moderno. O WPF fornece um conjunto abrangente de recursos de desenvolvimento de aplicativos que incluem XAML (eXtensible Application Markup Language), controles, associação de dados, layout, elementos gráficos 2D e 3D, animação, estilos, modelos, documentos, mídia, texto e tipografia. O WPF faz parte do .NET; portanto, você pode criar aplicativos que incorporam outros elementos da API .NET.[^1]

___

## Layout
No WPF há diversos *estilos* de layout, que permitem que você organize como ficar melhor sua aplicação, entre eles, tem o `grid`, estilo padrão baseado em linhas e colunas, e o `DockPanel`, que se assemelha a mini "conteineres" que ocupam todo o espaço dedicado.
___
### Grid
O grid, como já dito, usa-se linhas e colunas para definir seu layout, permitindo manter uma responsividade adequada ao aplicativo.

#### Linhas e Colunas
Para definir as linhas(row, em inglês), usa-se a tag `<Grid.RowDefinitions>`, e dentro dela, vc define as colunas a serem criadas usando a tag `<RowDefinition>`.
```
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition height="*" /> // Tamanho máximo disponível
        <RowDefinition height="Auto" /> // Ajuste automático de tamanho
    </Grid.RowDefinitions>
...
```
 Com o código acima, define-se duas linhas, uma ocupando todo o espaço disponível, e a outra se ajustando de acordo com o tamanho de seu conteúdo

Já para definir as colunas, segue-se o esquema de linhas, porém, obviamente, com nomes diferentes, nesse caso: `Column`
```
...
    <Grid.ColumnDefinitions>
        <ColumnDefinition height="*" /> // Segue-se o mesmo esquema
        <ColumnDefinition height="Auto" /> // Como dito no exemplo acima, tamanho "Auto"mático
    </Grid.ColumnDefinitions>
</Grid>
```


 <!-- Referências Bibliográficas -->
[^1]: Fonte: https://learn.microsoft.com/pt-br/dotnet/desktop/wpf/overview/?view=netdesktop-6.0