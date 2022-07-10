package coverage

import (
	"errors"
	"os"
	"strings"
	"testing"
	"time"
)

// DO NOT EDIT THIS FUNCTION
func init() {
	content, err := os.ReadFile("students_test.go")
	if err != nil {
		panic(err)
	}
	err = os.WriteFile("autocode/students_test", content, 0644)
	if err != nil {
		panic(err)
	}
}

// WRITE YOUR CODE BELOW

func TestSwap(t *testing.T) {
	people := People{{firstName:"Hasan"}, {firstName:"Turaj"}}
	peopleExpect := []string{"Turaj", "Hasan"}
	people.Swap(0,1)
	if peopleExpect[0] != people[0].firstName  {
	}else if peopleExpect[1] != people[1].firstName {
		t.Errorf("func swap working not correctly")
	}
}

func TestLen(t * testing.T) {
	people := People{{firstName: "Hasanbek"}, {firstName: "AyanPidr"}}
	res := people.Len()
	if res != 2 {
		t.Errorf("func Len working not correctly")
	}
}

func TestLess(t *testing.T) {
	people := People{{firstName: "Salima", lastName: "Kaliakparova", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),}, 
	{firstName: "Turaj", lastName: "Mehdidev", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 1, time.UTC),},

	{firstName: "Hasannn", lastName: "Mehdiedv", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),}, 
	{firstName: "Artur", lastName: "Mehddiev", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),},

	{firstName: "Salima", lastName: "Kaliakparova", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),}, 
	{firstName: "Salima", lastName: "Mehdiev", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),},

	{firstName: "August", lastName: "September", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),}, 
	{firstName: "August", lastName: "September", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),},


	{firstName: "Salima", lastName: "Kaliakparova", birthDay: time.Date(1986, 12, 5, 0, 1, 0, 0, time.UTC),}, 
	{firstName: "Turaj", lastName: "Mehdidev", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),},

	{firstName: "Hasan", lastName: "Mehdiedv", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),}, 
	{firstName: "Arturrrr", lastName: "Mehddiev", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),},

	{firstName: "Salima", lastName: "Mehddiev", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),}, 
	{firstName: "Salima", lastName: "Kaliakparova", birthDay: time.Date(1986, 12, 5, 0, 0, 0, 0, time.UTC),},
}

	f := false
	lessVar := people.Less(0,1)
	if lessVar == f {
		t.Errorf("func Less working not correctly")
	}
	lessVar = people.Less(2,3)
	if lessVar !=f {
		t.Errorf("func Less working not correctly")
	}
	lessVar = people.Less(4,5)
	if lessVar == f {
		t.Errorf("func Less working not correctly")
	}
	lessVar = people.Less(6,7)
	if lessVar != f {
		t.Errorf("func Less working not correctly")
	}


	lessVar = people.Less(8,9)
	if lessVar == f {
		t.Errorf("func Less working not correctly")
	}
	lessVar = people.Less(10,11)
	if lessVar != f {
		t.Errorf("func Less working not correctly")
	}
	lessVar = people.Less(12,13)
	if lessVar != f {
		t.Errorf("func Less working not correctly")
	}
}

func TestCols(t *testing.T) {
	m := &Matrix{
		rows: 2,
		cols: 2,
		data: []int{0,1,2,3},
	}
	except := [][]int{{0,2},{1,3}}
	got := m.Cols()

	for i := 0; i < len(except); i++ {
		if len(except[i]) != m.rows {
			t.Errorf("testing error: expected cols %d but got %d", len(except[i]), m.rows)
		}
	}
	for i := 0; i < len(except); i++ {
		for j := 0; j < len(except[i]); j ++ {
			if got[i][j] != except[i][j] {
				t.Errorf("Not matched excepted value %d but got %d", except[i][j], got[i][j])
			}
		}	
	}
}

func TestSet(t *testing.T) {
	m := &Matrix{
		rows: 1,
		cols: 2,
		data: []int{0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19},
	}
	tData := map[string]map[string]int {
		"normal" : {
			"row": 0,
			"col": 1,
			"value": 8,
			"answer": 1,
		},
		"err_col" : {
			"row": 0,
			"col": 3,
			"value": 8,
			"answer": 0,

		},
		"err_row" : {
			"row": 1,
			"col": 1,
			"value": 8,
			"answer": 0,

		},
		"err_minus" :{
			"row": -8,
			"col": 1,
			"value": 8,
			"answer": 0,

		},
	}
	for i, w := range tData {
		name, obj := i, w
		t.Run(name, func(t *testing.T) {
			t.Parallel()
			ans := obj["answer"]
			got := m.Set(obj["row"], obj["col"], obj["value"])
			if got && ans == 0 || !got && ans == 1 {
				t.Errorf("expected \"%t\" but got \"%t\"",!got, got)
			}
		})
	}
}

func TestRows(t *testing.T) {
	m := &Matrix{
		rows: 2,
		cols: 2,
		data: []int{0,1,2,3},
	}
	except := [][]int{{0,1},{2,3}}
	got := m.Rows()

	for i := 0; i < len(except); i++ {
		if len(except[i]) != m.cols {
			t.Errorf("testing error: expected cols %d but got %d", len(except[i]), m.rows)
		}
	}
	for i := 0; i < len(except); i++ {
		for j := 0; j < len(except[i]); j ++ {
			if got[i][j] != except[i][j] {
				t.Errorf("Not matched excepted value %d but got %d", except[i][j], got[i][j])
			}
		}	
	}
}


func TestNew(t *testing.T) {
	t.Parallel()
	tData := map[string]map[string]interface{}{
		"normal" : {
			"data" : "  0 1 2 3 4 5 6 7 8 9\n10 11 12 13 14 15 16 17 18 19  ",
			"exp_data" : Matrix{
				rows: 2,
				cols: 10,
				data: []int{0, 1, 2, 3, 4, 5, 6, 7, 8, 9,
					10, 11, 12, 13, 14, 15, 16, 17, 18, 19},
			},
			"exp_err" : nil,
		},
		"empty" : {
			"data" : " ",
			"exp_data" : nil,
			"exp_err" : errors.New("strconv.Atoi"),
		},
		"atoi_err" : {
			"data" : "0 1 2 3 4 5 6 7 8 9a\n 10 11 12 13 14 15 16 17 18 19",
			"exp_data" : nil,
			"exp_err" : errors.New("strconv.Atoi"),
		},
		"cols_err" : {
			"data" : "0 1 2 3 4 5 6 7 8 9\n 10 11 12 13 14 15 16 17 18",
			"exp_data" : nil,
			"exp_err" : errors.New("Rows need to be the same length"),
		},
	}

	for k, v := range tData {
		name, obj := k, v
		t.Run(name, func(t *testing.T) {
			t.Parallel()
			got, err := New(obj["data"].(string))
			if err != nil {
				exp_err := obj["exp_err"].(error)
				if ((name == "atoi_err" || name == "empty") && !strings.HasPrefix(err.Error(), exp_err.Error())) ||
				name == "cols_err" && err.Error() != exp_err.Error() {
					t.Fatalf("unexpected error: %s",err.Error())
				}
				return // for "ok error"
			}
			expire := obj["exp_data"].(Matrix)
			// catching error if testing data given with error
			if got.cols != expire.cols || got.rows != expire.rows || len(expire.data) != len(got.data) { 
				t.Fatalf("testing error: check given exp_data with given data, cols(%d-%d), rows(%d-%d), len(%d-%d),",
				expire.cols, got.cols,expire.rows,got.rows,len(expire.data),len(got.data))
			}
			// catching error if testing data given with error - end
			for i, d := range expire.data {
				if got.data[i] != d {
					t.Errorf("data not match: expected %d but got %d",d,got.data[i])
				}
			}
		})
	}
}