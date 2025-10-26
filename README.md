# assignment9.R
<br>
<br>
<h4>There are many different ways to graph and visualize data to the viewer. What it comes down to is how comfortable the programmer is with the library and the capabilities of the library. The graphs that can be represented with different libraries share basic similarities. 
<br>
<br>
     
Base R - Great for creating basic and simple graphs. Syntax is very straight-forward. Additional layers would be difficult to add.
<br>
<br>     
     
Lattice - The syntax was a little confusing to understand since the y comes before the x. A step up from Base R, in my opinion, for adding additional layers to the graphs. Not basic graphs but not as customizable as other libraries.
     
<br>
<br>
Ggplot2 - Most preferred library, in my opinion, for customization and adding multiple layers. This might be possible for other libraries but the syntax is straight forward and easy to understand. 
<br>
<br>
<br>

Conclusion - When writing “publication‑quality” code, I would always prefer to use ggplot2 for my graphs. I enjoy the customization of the graph and how many layers I can add to the graph without it becoming cumbersome. I was pleasantly surprised with how easy to use Base R was and how quickly I could spin up a graph. Lattice was neither easy or very customizable. It was in the middle of the two graphs and I didn't find much enjoyment using it. With time, each graph could be used with high skill, but out of the box I prefer ggplot2 the most.

</h4>
<br>
<br>
--------------------------------------------------BASE R--------------------------------------------------
<br>
<br>
## Scatter plot
plot(data$mpg, data$wt,
     main   = "Base: MPG vs. WT",
     xlab   = "MPG",
     ylab   = "WT")

<img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/65a3a511-fa43-4382-ae73-9f9293dc6749" />


## Histogram
hist(data$mpg,
     main   = "Base: Distribution of mpg",
     xlab   = "mpg")

<img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/f1b33d7d-13cc-4155-aa9e-7c5e00ebaf9c" />
<br>
<br>


--------------------------------------------------LATTICE--------------------------------------------------
<br>
<br>
## Conditional scatter plot (small multiples)
xyplot(mpg ~ hp | factor(cyl),
       data = data,
       main = "Lattice: mpg vs hp by cylinder")

<img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/64b55545-1242-4920-86a7-dd4d409fa194" />


## Box-and-whisker plot
bwplot(mpg ~ factor(cyl),
       data = data,
       main = "Lattice: mpg by cylinder")

<img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/e39c9c5f-cea9-4576-93d1-8382abca0ee8" />

<br>
<br>

--------------------------------------------------GGPLOT2--------------------------------------------------
<br>
<br>

## Scatter plot with smoothing
ggplot(data, aes(x = cyl, y = mpg, fill = wt, size = hp)) +
  geom_point(shape = 21, color = "black", stroke = 1) +
  scale_x_continuous(breaks = c(4,6,8)) +
  scale_fill_gradient(low = "blue", high = "red") +
  labs(title = "ggplot2: cyl by mpg filled by wt sized by hp")

<img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/aea02f10-122b-42bc-b04b-00ca5e9a06d9" />


## Faceted histogram
ggplot(data, aes(mpg)) +
  geom_histogram(binwidth = 1) +
  facet_wrap(~ cyl) +
  labs(title = "ggplot2: mpg distribution by cyl")

  <img width="1344" height="960" alt="image" src="https://github.com/user-attachments/assets/f34dad17-db5b-42b9-a6ca-d7f13bd9b8c1" />

