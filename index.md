---
title       : Child Weight Prediction Project
subtitle    : Developing Data Products Project
author      : LR
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Sensitive theme

### Everybody cares about children

---

## Super tremendeously complex computation

server.R:


```r
library(shiny)

predict <- function(age) 3 * age + 7

shinyServer(
  function(input, output) {
    output$inputValue <- renderPrint({input$age})
    output$prediction <- renderPrint({predict(input$age)})
  }
)
```

---

## Beautiful but still simple UI

ui.R:


```r
library(shiny)

shinyUI(pageWithSidebar(
  headerPanel("Child weight prediction (1 - 13 years)"),
  sidebarPanel(
    h3('Controllbar'),
    sliderInput("age", "Age (in years):", min = 1, max = 13, value = 10)
  ),
  mainPanel(
    h3('Results of child weight prediction'),
    h4('Age you entered (in years) '),
    verbatimTextOutput("inputValue"),
    h4('Which resulted in a weight prediction (in kg) '),
    verbatimTextOutput("prediction")
  )
))
```

---

## Conclusion

Great technologies to play with ;)


