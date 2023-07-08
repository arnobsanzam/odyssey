---
title: "Problem Solving"
date: "2023-07-08"
author: "Syed Sanzam"
---

## 01. Find frequency of each character in a String

```java
@ExtendWith(MockitoExtension.class)
@Slf4j
public class Problem {

    @Test
    public void verify() {
        final String str = "abcceedf";
        log.info(solution1(str).toString());
        log.info(solution2(str).toString());
        log.info(solution3(str).toString());
        log.info(solution4(str).toString());
    }

    Map<Character, Integer> solution1(String str) {
        Map<Character, Integer> map = new HashMap<>();
        for (Character c : str.toCharArray()) {
            map.put(c, map.getOrDefault(c, 0) + 1);
        }
        return map;
    }

    Map<Character, Integer> solution2(String str) {
        Map<Character, Integer> map = new HashMap<>();
        for (Character c : str.toCharArray()) {
            map.compute(c, (key, value) -> value == null ? 1 : ++value);
        }
        return map;
    }

    Map<Character, Integer> solution3(String str) {
        return str.chars()
                .mapToObj(c -> (char) c)
                .collect(Collectors.toMap(
                        c -> c,
                        c -> 1,
                        (existingValue, newValue) -> existingValue + newValue
                ));
    }

    Map<Character, Long> solution4(String str) {
        return str.chars()
                .mapToObj(c -> (char) c)
                .collect(Collectors.groupingBy(c -> c, Collectors.counting()));
    }
}
```

> In *Solution 3*, `str.chars()` method is used to convert the input string to an IntStream, which represents a sequence of integer values. Each integer value in the IntStream corresponds to the Unicode value of a character in the str string.The `mapToObj` operation is used to convert the IntStream of integer values back to a Stream<Character> by performing a typecast for each value. It is necessary to work with characters rather than integers when collecting them into a map.

> In *Solution 4*, the `groupingBy()` operation groups the characters by their values and produces a map where the keys are the characters, and the values are the counts of their occurrences in the original string. 
