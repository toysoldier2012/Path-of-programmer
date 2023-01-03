 常用方法
		  增
		  boolean add(E e)
		  boolean addAll(Collection<? extends E> c)
		  删
		  boolean remove(Object o)
		  boolean removeAll(Collection<?> c)
		  void clear()
		  default boolean removeIf(Predicate<? super E> filter)
		  改
		  boolean retainAll(Collection<?> c)
		  查
		  boolean contains(Object o)
		  boolean containsAll(Collection<?> c)
		  Object[] toArray()
		  <T> T[] toArray(T[] a)
		  给定数组长度小于集合的大小，则会重新创建一个大小与集合相等的数组，并且传入数据
		  给定数组长度等于集合的大小，直接传入数据
		  给定数组长度大于集合的大小，多余的数组位用null代替
		  boolean isEmpty()
		  int size()
		  default Stream<E> stream() 高级版的.iterator()
		  default Stream<E> parallelStream() 并发Stream