---
title: Python 에서의 Hadoop
date: 2024-09-12 16:20:00 +09:00
categories: [Project, 논문]
tags:
  [
    Project,
    WEB,
    DATA,
    Hadoop,
    웹 서비스,
    분산처리,
    파이썬,
    .
    .
    .
  ]
---


# 1. Hadoop, Java VS Python

Hadoop의 MapReduce 작업은 **Java**로 구현하는 것이 더 적합할 때가 많습니다. 그 이유는 다음과 같습니다:

1. **Hadoop의 기본 언어**: Hadoop 자체가 Java로 작성되어 있어, MapReduce 작업을 Java로 작성하면 더 좋은 성능을 기대할 수 있습니다. Hadoop의 주요 API들도 Java를 기반으로 설계되어 있어, 작업 통합이 더 원활합니다.

2. **성능**: Java는 네이티브로 Hadoop과 통합되기 때문에 Python보다 빠를 수 있습니다. 대용량 데이터 처리에서는 성능이 중요한데, Python은 Java보다 인터프리터 방식으로 동작하므로 속도가 느릴 수 있습니다.

그러나, Python을 사용할 수도 있는 경우가 있습니다:

1. **PyDoop 또는 Hadoop Streaming**: Python을 선호한다면 `Hadoop Streaming`이나 `PyDoop` 같은 툴을 사용할 수 있습니다. 이들은 Python 스크립트를 사용해 MapReduce 작업을 수행할 수 있게 해줍니다. 파이썬 코드는 쓰기 쉽고, 테스트 및 디버깅이 간단할 수 있습니다.
   
2. **데이터 과학 및 머신러닝**: Python은 데이터 처리와 분석, 특히 머신러닝에 강력한 라이브러리(예: Pandas, NumPy, Scikit-learn)를 제공하므로, 이를 활용할 수 있습니다.

**결론**: Hadoop에서 성능과 네이티브 통합이 중요한 경우에는 **Java**를 사용하는 것이 좋고, Python으로도 가능하지만 약간의 성능 저하를 감수해야 합니다.



# 2. Hadoop Mapreduce on Python Env.

**Hadoop Streaming**과 **PyDoop**은 모두 Python으로 Hadoop MapReduce 작업을 수행할 수 있는 방법을 제공합니다. 두 도구는 각각 다른 방식으로 동작하며, Python을 사용한 분산 데이터 처리에 유용합니다.

### 1. **Hadoop Streaming**

**Hadoop Streaming**은 Hadoop의 MapReduce 프레임워크에서 제공하는 기본 기능으로, **Java가 아닌 언어로 MapReduce 작업을 수행할 수 있는 방법**입니다. 이 방식에서는 표준 입력과 표준 출력을 사용하여 Mapper와 Reducer를 호출할 수 있습니다.

#### 특징:
- **언어 독립적**: Python, Perl, Ruby, Bash 등 표준 입출력을 처리할 수 있는 모든 언어로 Mapper와 Reducer를 작성할 수 있습니다.
- **사용 방법**: 사용자 스크립트가 표준 입력으로 데이터를 받고, 표준 출력으로 결과를 내보내도록 설계되면 됩니다. Hadoop이 이를 받아 분산 처리합니다.

#### 동작 방식:
- Mapper와 Reducer 스크립트는 각각 표준 입력(STDIN)으로 데이터를 읽고, 표준 출력(STDOUT)으로 결과를 출력하는 형태로 작성됩니다.
- Hadoop은 이러한 스크립트와 데이터를 통신하게 하여 MapReduce 작업을 처리합니다.
  
#### 예시 (Python으로 Mapper와 Reducer 작성):

**Mapper (mapper.py):**
```python
import sys
for line in sys.stdin:
    words = line.strip().split()
    for word in words:
        print(f"{word}\t1")
```

**Reducer (reducer.py):**
```python
import sys
from collections import defaultdict

word_count = defaultdict(int)
for line in sys.stdin:
    word, count = line.strip().split('\t')
    word_count[word] += int(count)

for word, count in word_count.items():
    print(f"{word}\t{count}")
```

**실행 명령어:**
```bash
hadoop jar $HADOOP_HOME/share/hadoop/tools/lib/hadoop-streaming-*.jar \
    -input /path/to/input \
    -output /path/to/output \
    -mapper "python mapper.py" \
    -reducer "python reducer.py"
```

#### 장점:
- **언어 제약 없음**: Python을 비롯한 다양한 언어로 쉽게 MapReduce 작업을 수행할 수 있습니다.
- **단순함**: Hadoop을 처음 접하거나, 작은 규모의 작업에 적합합니다.

#### 단점:
- **성능 저하**: Hadoop Streaming은 자바 네이티브 API를 사용하는 것보다 약간 느릴 수 있습니다.
- **제한된 기능**: 고급 기능을 활용하기 위해서는 Java MapReduce가 필요할 때가 있습니다.

---

### 2. **PyDoop**

**PyDoop**은 Hadoop의 API를 직접 Python에서 사용할 수 있게 해주는 라이브러리입니다. Hadoop의 핵심 기능을 Python 코드로 좀 더 네이티브하게 구현할 수 있도록 돕습니다.

#### 특징:
- **Hadoop API 직접 호출**: PyDoop을 사용하면 Hadoop의 Java API를 Python에서 사용할 수 있습니다. 이는 Hadoop 파일 시스템(HDFS)과 MapReduce 인터페이스에 대한 더 나은 제어를 제공합니다.
- **더 나은 성능**: Hadoop Streaming보다 더 나은 성능을 기대할 수 있으며, Python 코드에서 네이티브 Hadoop 기능을 사용하게 됩니다.
- **HDFS 직접 접근**: PyDoop은 HDFS를 직접 다룰 수 있는 기능을 제공하여, 파일을 읽고 쓰는 작업을 쉽게 수행할 수 있습니다.

#### 동작 방식:
- PyDoop은 Hadoop의 MapReduce 프레임워크와 유사한 방식으로 동작하지만, Python으로 좀 더 세밀한 제어가 가능합니다. 또한, HDFS와의 통합이 강화되어 있어 데이터 입출력이 수월합니다.

#### 설치:
```bash
pip install pydoop
```

#### 예시 (PyDoop으로 MapReduce 작업):

**Mapper (word_count_mapper.py):**
```python
import pydoop.mapreduce.api as api

class Mapper(api.Mapper):
    def map(self, context):
        words = context.value.split()
        for word in words:
            context.emit(word, 1)
```

**Reducer (word_count_reducer.py):**
```python
import pydoop.mapreduce.api as api

class Reducer(api.Reducer):
    def reduce(self, context):
        total = sum(context.values)
        context.emit(context.key, total)
```

**실행 명령어:**
```bash
pydoop submit --upload-file-to-cache word_count_mapper.py word_count_reducer.py \
    word_count_mapper.py word_count_reducer.py \
    -input /path/to/input -output /path/to/output
```

#### 장점:
- **더 나은 성능**: Hadoop Streaming보다 더 좋은 성능을 제공할 수 있습니다.
- **Hadoop과의 통합**: Python으로 작성하면서도 Hadoop API와 직접 상호작용이 가능합니다.
- **HDFS 통합**: PyDoop은 HDFS 파일 시스템과 직접 상호작용할 수 있어서 파일 읽기/쓰기 작업이 용이합니다.

#### 단점:
- **복잡성**: Java MapReduce에 익숙하다면 PyDoop은 상대적으로 복잡할 수 있습니다.
- **설정 요구**: PyDoop을 사용하는 설정이 다소 까다로울 수 있습니다.

---

### 결론:
- **Hadoop Streaming**은 간단한 작업을 Python으로 빠르게 구현하고자 할 때 유용하며, 언어 제약 없이 다양한 언어를 사용할 수 있다는 장점이 있습니다.
- **PyDoop**은 성능을 고려하면서도 Python을 사용하고 싶은 경우 적합하며, Hadoop의 더 고급 기능을 활용해야 할 때 유리합니다.
