# CreatePerTickValue.cs
Determine "value", that is possible profit, at each bar of stock/futures data. This program creates such a target value
for stock/futures data series.

Basically, the idea is, at each point in time, you would like to know that if you went long, would you make some money
before some max trailing loss. By trailing loss, I mean, when you enter, you might have a max loss of $100. After some time,
if that loss was not hit, you might hit some profit floor, say $100, where you move your stop up to $0. Fom then on, each
time you make another $100, you move up your stop by $100, so you never lose more than $100 from your max.

Now, the stop values don't all have to be the same amount. You first, basic stop loss could be $100. The breakeven stop floor
could be when you've made $200. The trailing stop could be yet again a different amount, and that amount could change based
on the total profit in the trade (you could make the stop either tighter or looser). Also, you could adjust the stop if the
trade flattened out, or you could just exit if the trade flattened out. Also, you could have a n-bars stop and a profit stop.
Lots of different possibilities.

Right now, this program computes the value of each bar based on having 1) fixed loss stop, 2) a break-even floor equal to that stop
loss, and 3) a trailing stop equal to that stop loss.
