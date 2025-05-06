# stats500-homework-4-solved
**TO GET THIS SOLUTION VISIT:** [STATS500 Homework 4 Solved](https://www.ankitcodinghub.com/product/stats500-homework-4-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;96610&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;STATS500 Homework 4 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
<pre>set.seed(48109711)
n&lt;-200; x&lt;-rnorm(2*n); x1&lt;-x[1:n]; x2&lt;-x[(n+1):(2*n)]
x3&lt;-.7*x1+.9*x2+rnorm(n)*.1
beta&lt;-c(1, 1, 1, 2)
y1&lt;-beta[1]+beta[2]*x1+beta[3]*x2+rnorm(n)*.3
y2&lt;-beta[1]+beta[2]*x1+beta[3]*x2+beta[4]*x3+rnorm(n)*.3
dat&lt;-data.frame(y1=y1,y2=y2,x1=x1,x2=x2,x3=x3)
outx12 &lt;- lm(y1~x1+x2, data=dat)
summary(outx12)
outx123 &lt;- lm(y2~x1+x2+x3, data=dat)
library(ellipse)
## Plot the confidence region
par(mfrow=c(1,2))
plot(ellipse(outx12, c("x1", "x2")), type="l")
points(coef(outx12)[2], coef(outx12)[3], pch=18)
plot(ellipse(outx123, c("x1", "x2")), type="l")
points(coef(outx123)[2], coef(outx123)[3], pch=18)
D1&lt;- model.matrix(outx12);D2&lt;- model.matrix(outx123)
cov(x1,x2);
V1&lt;-solve(t(D1)%*%D1); V2&lt;-solve(t(D2)%*%D2);
round(V1[2:3,2:3],4); round(V2[2:3,2:3],4);
</pre>
<ol>
<li>In the codes given above, we generate n = 200 x1, x2 and x3, and x1, x2 are independent of each other. In model A, we generate y1 with the predictors x1 and x2. In model B, we generate y2 with all three predictors. In the two plots we generate, we obtain the 95% confidence regions for the coefficients, βx1, βx2 from each of the two models. Note that even you generate x1 and x2 independently, the sample correlation still may not be 0, but it tends to be small. Consequently, the major axis and minor axis of the ellipse are roughly parallel with the x-axis and y-axis corresponding to βˆx1, βˆx2. In model B, you are using the same x1 and x2 and you still consider the 95% confidence ellipse for βx1, βx2, do you expect the major axis and minor axis of the ellipse are roughly parallel with the x-axis and y-axis corresponding to βˆx1, βˆx2? Please briefly explain your answer using the output you obtain. Basically, in a multiple regression, unless the predictors are completely orthogonal to each other, the estimated coefficients and the corresponding inference are adjusted to the existence of other predictors.</li>
<li>Using the teengamb dataset, fit a model to predict gambling expenditure from all other available variables. Use “help(“teengamb”) to see more descriptions about this data set. You can start with a linear regression with the predictors sex, status, income and verbal. Consider the following two Y :
• Yorg = teengamb$gamble.

• Ylog = log(teengamb$gamble + 1).
</li>
</ol>
</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
Perform regression diagnostics on these models and compares the answers to the follow- ing questions based on the two models. Display only those plots that are relevant to the questions below. Present your diagnostics in a logical order.

(a) Check the existence of patterns in the residual against fitting values. Are the residuals centering at 0 in all areas of fitted values?

(b) Check the constant variance assumption for the errors.

(c) Check the normality assumption. Do you need to check normality of both models (one only check normality when the residuals center at zero and roughly share a constant variance.)

3. Now focus on the regression model with the response Ylog = log(teengamb$gamble+1). What would be the 95% prediction interval for the gambling expenditure per year for a boy with status = 40, income =2, verbal score = 6? (Hint: you should transform the prediction interval back to the original scale).

</div>
</div>
</div>
