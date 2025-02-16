TestIterator.java:

    Does using a LinkedList instead of an ArrayList make a difference?
        Using a LinkedList instead of an ArrayList does not significantly affect iteration behavior,
          but the underlying performance differs. LinkedList allows faster insertions/removals (O(1)
            with an iterator), while ArrayList provides faster random access (O(1)).

    What happens if you use list.remove(Integer.valueOf(77)) instead of i.remove()?
        When using [list.remove(Integer.valueOf(77))] instead of [i.remove()], it
            would remove only the first occurrence instead of all occurrences.

List.java:

    Does using a LinkedList instead of an ArrayList make a difference?
        Using a LinkedList instead of an ArrayList affects performance
            but not functionality. LinkedList is better for frequent
                insertions/removals, while ArrayList is faster for
                    random access due to contiguous memory  storage.

    What does list.remove(5) do?
        this removes the 6th element (on index-based)

    What does list.remove(Integer.valueOf(5)) do?
        this removes the actual value, and not the element

Performance.java:

    What conclusions can you draw about the performance of LinkedList vs. ArrayList when comparing their running times for AddRemove vs. Access?
    Record those running times in README.txt!

        ArrayList generally has faster access time (get()) because it uses an array internally, making it efficient for random access.
            However, adding or removing elements at the beginning of the list is slower due to the shifting of elements.

        LinkedList, on the other hand, has slower access time (get()) because it has to traverse the list from the start (or end) to
            find the element, but it performs better for adding and removing elements at the beginning or middle since it doesn’t
                need to shift other elements.


        Performance results for different list sizes:
,______________________________________________________________
|            Size (N)            |   10  | 100 | 1000 | 10000 |
| Time for LinkedList.add/remove | 968ms |  1s |  4s  |  54s  |
| Time for ArrayList.add/remove  | 983ms |  1s |  4s  |  54s  |
|    Time for LinkedList.get     |  ~1s  | ~2s | ~3s  |  ~4s  |
|    Time for ArrayList.get      |  ~1s  | ~2s | ~3s  |  ~4s  |
```````````````````````````````````````````````````````````````

Conclusions on LinkedList vs. ArrayList performance:

    ArrayList is faster for get() operations because it
        uses contiguous memory (O(1) access time).

    LinkedList is faster for add(0, element) and remove(0)
        because it does not require shifting elements.

    As N increases, the performance gap widens, favoring
        ArrayList for access-heavy operations and LinkedList
            for frequent insertions/removals.