# .check_na() works

    Code
      .check_na(c(1, NA), allow_na = FALSE)
    Condition
      Error:
      ! `c(1, NA)` must not contain NA values.
      * NA locations: 2

# .check_size() works

    Code
      .check_size(1:5, 6, 10)
    Condition
      Error:
      ! `1:5` must have size >= 6.
      x 5 is too small.

---

    Code
      .check_size(1:5, 1, 4)
    Condition
      Error:
      ! `1:5` must have size <= 4.
      x 5 is too big.

# .check_scalar() works

    Code
      .check_scalar(1:2)
    Condition
      Error:
      ! `1:2` must be a single <integer>.
      x `1:2` has 2 values.

---

    Code
      .check_scalar(NULL, allow_null = FALSE)
    Condition
      Error:
      ! `NULL` must be a single <non-NULL>.
      x `NULL` has no values.

---

    Code
      .check_scalar(character(), allow_zero_length = FALSE)
    Condition
      Error:
      ! `character()` must be a single <character (non-empty)>.
      x `character()` has no values.

# .check_x_no_more_than_y() works

    Code
      .check_x_no_more_than_y(2, 1)
    Condition
      Error:
      ! `2` can't be larger than `1`.
      * `2` = 2
      * `1` = 1

