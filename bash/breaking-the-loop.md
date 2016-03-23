```bash
cat /tmp/break.sh 
for i in 1 2 3
do
  for j in a b c
  do
    if [ $j = b ] && [ $i = 2 ]
    then
      break
    fi
    echo $i $j
  done
done
# $? 0
# ./ ~
# t  0
bash /tmp/break.sh 
1 a
1 b
1 c
2 a
3 a
3 b
3 c
```

```bash
cat /tmp/break2.sh 
for i in 1 2 3
do
  for j in a b c
  do
    if [ $j = b ] && [ $i = 2 ]
    then
      break 2
    fi
    echo $i $j
  done
done
# $? 0
# ./ ~
# t  0
bash /tmp/break2.sh 
1 a
1 b
1 c
2 a
```

`break` and `continue` can be used on the outer loop by passing a number
