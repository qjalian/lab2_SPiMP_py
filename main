from collections import deque
from concurrent.futures import ThreadPoolExecutor

def process_channel(queue):
    data = []

    while queue:
        count = queue.popleft()
        subArray = [queue.popleft() for _ in range(count)]
        data.append(subArray)

    return data

def main():
    queue = deque([3, 4, 0, 2, 1, 2, 2, 4, 5])

    with ThreadPoolExecutor() as executor:
        data_future = executor.submit(process_channel, queue)
    #Получение ожидаемого результата
    data = data_future.result()

    for subArray in data:
        print("[", end=" ")
        print(*subArray, end=" ")
        print("]")

if __name__ == "__main__":
    main()
