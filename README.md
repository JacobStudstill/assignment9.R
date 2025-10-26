# assignment9.R

--------------------------------------------------BASE R--------------------------------------------------

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



--------------------------------------------------LATTICE--------------------------------------------------

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



--------------------------------------------------GGPLOT2--------------------------------------------------

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

