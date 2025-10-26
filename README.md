# assignment9.R

# Scatter plot
plot(data$mpg, data$wt,
     main   = "Base: MPG vs. WT",
     xlab   = "MPG",
     ylab   = "WT")


# Histogram
hist(data$mpg,
     main   = "Base: Distribution of mpg",
     xlab   = "mpg")


# Conditional scatter plot (small multiples)
xyplot(mpg ~ hp | factor(cyl),
       data = data,
       main = "Lattice: mpg vs hp by cylinder")


# Box-and-whisker plot
bwplot(mpg ~ factor(cyl),
       data = data,
       main = "Lattice: mpg by cylinder")


# Scatter plot with smoothing
ggplot(data, aes(x = cyl, y = mpg, fill = wt, size = hp)) +
  geom_point(shape = 21, color = "black", stroke = 1) +
  scale_x_continuous(breaks = c(4,6,8)) +
  scale_fill_gradient(low = "blue", high = "red") +
  labs(title = "ggplot2: cyl by mpg filled by wt sized by hp")


# Faceted histogram
ggplot(data, aes(mpg)) +
  geom_histogram(binwidth = 1) +
  facet_wrap(~ cyl) +
  labs(title = "ggplot2: mpg distribution by cyl")
