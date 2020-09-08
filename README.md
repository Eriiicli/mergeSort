# mergeSort
# Use divide-and-conquer method
# Code is in the below：

# coding:utf-8

def mergeSort(listx):
    length = len(listx)
    if length <= 1:
        return listx
    #数组分割线：
    split = length // 2
    #递归调用本函数，进行归并排序：
    l_list = mergeSort(listx[:split])
    r_list = mergeSort(listx[split:])
    #定义一个空列表，存储归并排序后的元素：
    mlist = []
    #定义两个游标：
    lCursor, rCursor = 0, 0
    while lCursor < len(l_list) and rCursor < len(r_list):
        if l_list[lCursor] <= r_list[rCursor]:
            mlist.append(l_list[lCursor])
            lCursor += 1
        else:
            mlist.append(r_list[rCursor])
            rCursor += 1
    mlist += l_list[lCursor:]
    mlist += r_list[rCursor:]
    return mlist

#功能测试：
if __name__ == "__main__":
    list = [23, 2, 59, 102, 29, 58, -10, 201, 268, -300]
    print(list)
    list_merge = mergeSort(list)
    print(list)
    print(list_merge)
