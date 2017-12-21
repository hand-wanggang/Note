配货单1
1   SKU quantity  { A B C D}
2   SKU quantity  { A B E F H}
3   SKU quantity  { A E F H G I}
4   SKU quantity  { A T B F H}

But: A  是门店 , B 是EC 仓  F 是RDC。 是发门店还是EC仓？


配货单2
1   SKU quantity  { A  B C D }
2   SKU quantity  { A B E F H }
3   SKU quantity  { E F H G I }
4   SKU quantity  { A T F H }

But: A  是门店 , B 是EC 仓  F 是RDC  C可以到7 D可以到5  H->]7？

可选的拆单方案:
{[1 2 4] ,[3]} ,{[1,2],[3,4]},{[1],[2,3,4]}
{  [A]   ,[..]},{[A,B],[F,H]},{[..],[F]}
