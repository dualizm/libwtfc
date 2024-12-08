# libwtfc
Library of wrapped types for C.

## Types

| old immutable types      | new immutable types | old mutable types  | new mutable types |
| ------------------------ | ------------------- | ------------------ | ----------------- |
| uint8_t const            | u8                  | uint8_t            | mut_u8            |
| uint16_t const           | u16                 | uint16_t           | mut_u16           |
| uint32_t const           | u32                 | uint32_t           | mut_u32           |
| uint64_t const           | u64                 | uint64_t           | mut_u64           |
| int8_t const             | i8                  | int8_t             | mut_i8            |
| int16_t const            | i16                 | int16_t            | mut_i16           |
| int32_t const            | i32                 | int32_t            | mut_i32           |
| int64_t const            | i64                 | int64_t            | mut_i64           |
| float const              | f32                 | float              | mut_f32           |
| double const             | f64                 | double             | mut_f64           |
| long double const        | f128                | long double        | mut_f128          |
| uint_fast8_t const       | uf8                 | uint_fast8_t       | mut_uf8           |
| uint_fast16_t const      | uf16                | uint_fast16_t      | mut_uf16          |
| uint_fast32_t const      | uf32                | uint_fast32_t      | mut_uf32          |
| uint_fast64_t const      | uf64                | uint_fast64_t      | mut_uf64          |
| int_fast8_t const        | if8                 | int_fast8_t        | mut_if8           |
| int_fast16_t const       | if16                | int_fast16_t       | mut_if16          |
| int_fast32_t const       | if32                | int_fast32_t       | mut_if32          |
| int_fast64_t const       | if64                | int_fast64_t       | mut_if64          |
| uint_least8_t const      | ul8                 | uint_least8_t      | mut_ul8           |
| uint_least16_t const     | ul16                | uint_least16_t     | mut_ul16          |
| uint_least32_t const     | ul32                | uint_least32_t     | mut_ul32          |
| uint_least64_t const     | ul64                | uint_least64_t     | mut_ul64          |
| short const              | Short               | short              | mut_short         |
| int const                | Int                 | int                | mut_int           |
| long const               | Long                | long               | mut_long          |
| long long const          | LLong               | long long          | mut_llong         |
| unsigned short const     | UShort              | unsigned short     | mut_ushort        |
| unsigned int const       | UInt                | unsigned int       | mut_uint          |
| unsigned long const      | ULong               | unsigned long      | mut_ulong         |
| unsigned long long const | ULLong              | unsigned long long | mut_ullong        |
| uintptr_t const          | uptr                | uintptr_t          | mut_uptr          |
| intptr_t const           | iptr                | intptr_t           | mut_iptr          |
| size_t const             | usz                 | size_t             | mut_usz           |
| ptrdiff_t const          | dptr                | ptrdiff_t          | mut_dptr          |
| uintmax_t const          | umax                | uintmax_t          | mut_umax          |
| intmax_t const           | imax                | intmax_t           | mut_imax          |
| char16_t const           | ch16                | char16_t           | mut_ch16          |
| char32_t const           | ch32                | char32_t           | mut_ch32          |
| char const\*             | str                 | char \*            | mut_str           |
| char16_t const\*         | str16               | char16_t \*        | mut_str16         |
| char32_t const\*         | str32               | char32_t \*        | mut_str32         |

## Usage

```c

#include "wtfc.h"

#include <stdio.h>
#include <stdlib.h>

mut_int main(void) {
  i32 x = 34;
  i32 y = 8;
  printf("x + y = %" PRIi32 "\n", x + y);

  return EXIT_SUCCESS;
}

```

```c

#include "wtfc.h"

usz strnlen16(str16 text, usz limit) {
  if (!text)
    return 0;

  str16 iter = text;
  mut_usz limit_iter = limit;
  for (; *iter && limit_iter--; ++iter)
    ;

  return (usz)(iter - text);
}

```
