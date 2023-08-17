import math


def isPrime(n):
    if n < 2:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True


def convert_to_binary(k) -> []:
    result = []
    while k > 0:
        i = k % 2
        result.append(k)
        k = k // 2
    result.reverse()
    return result


def algorithm_square(a, r, n):
    k = convert_to_binary(r)
    k.reverse()

    A = a
    if k[0] == 1:
        b = a
    else:
        b = 1
    for i in range(1, len(k)):
        A = int((A ** 2) % n)
        if k[i] == 1:
            b = int((A * b) % n)
    return b


def main():
    a = int(input("Enter a :"))
    r = int(input("Enter b :"))
    n = int(input("Enter n :"))
    result = algorithm_square(a, r, n)
    print(result)
    if isPrime(result) == True:
        print("isPrime")
    else:
        print("not isPrime")


# ===========
if __name__ == '__main__':
    main()
