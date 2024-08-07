package main

import "fmt"

func main() {
    // Khởi tạo slice
    s := []int{1, 2, 3, 4, 5}
    fmt.Println("Initial slice:", s)

    // Thêm phần tử vào slice
    s = append(s, 6, 7)
    fmt.Println("Slice after appending:", s)

    // Tạo slice từ mảng
    arr := [5]int{10, 20, 30, 40, 50}
    s2 := arr[1:4]
    fmt.Println("Slice from array:", s2)

    // Duyệt qua slice
    fmt.Println("Elements in slice:")
    for _, value := range s {
        fmt.Println(value)
    }

    // Sử dụng hàm make để tạo slice
    s3 := make([]int, 5)
    fmt.Println("Slice created with make:", s3)

    // Thay đổi phần tử trong slice
    s3[0] = 100
    fmt.Println("Slice after modification:", s3)

    // In chiều dài và dung lượng của slice
    fmt.Println("Length and capacity of slice s3:", len(s3), cap(s3))
}

# Slice literals

package main

import "fmt"

func main() {
	q := []int{2, 3, 5, 7, 11, 13}
	fmt.Println(q)

	r := []bool{true, false, true, true, false, true}
	fmt.Println(r)

	s := []struct {
		i int
		b bool
	}{
		{2, true},
		{3, false},
		{5, true},
		{7, true},
		{11, false},
		{13, true},
	}
	fmt.Println(s)
}
