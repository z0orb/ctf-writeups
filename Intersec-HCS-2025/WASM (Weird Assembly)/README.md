# WASM (Weird Assembly)
### Description: Aku buat program yang nyusun bouquet buat orang yang spesial. Tapi pas aku balik ke komputer ku kok programnya malah jadi kaya code assembly aneh ya? ps. coba kalian bikin bouquet terbaik buat orang yang spesial 💐

Based on the challenge title, and the description, we can deduce that we're going to deal with Assembly.

We are given a file (no extension): ```for_that_special_someone```.

At first, based on the nature of the challenge category (Reverse Engineering), i thought we're dealing with a binary file. But i ran
```
file for_that_special_someone
```

and revealed that it actually was an ASCII text file:

![alt text](image.png)

So we cat it open:
```
❯ cat for_that_special_someone
   0           RESUME                   0

   1           BUILD_MAP                0

   2           LOAD_CONST               0 ('A')
               LOAD_CONST               1 ('Rose ')

   1           MAP_ADD                  1

   3           LOAD_CONST               2 ('B')
               LOAD_CONST               3 ('Camellia ')

   1           MAP_ADD                  1

   4           LOAD_CONST               4 ('C')
               LOAD_CONST               5 ('Magnolia ')

   1           MAP_ADD                  1

   5           LOAD_CONST               6 ('D')
               LOAD_CONST               7 ('Poppy ')

   1           MAP_ADD                  1

   6           LOAD_CONST               8 ('E')
               LOAD_CONST               9 ('Tulip ')

   1           MAP_ADD                  1

   7           LOAD_CONST              10 ('F')
               LOAD_CONST              11 ('Chrysanthemum ')

   1           MAP_ADD                  1

   8           LOAD_CONST              12 ('G')
               LOAD_CONST              13 ('Hyacinth ')

   1           MAP_ADD                  1

   9           LOAD_CONST              14 ('H')
               LOAD_CONST              15 ('Violet ')

   1           MAP_ADD                  1

  10           LOAD_CONST              16 ('I')
               LOAD_CONST              17 ('Lavender ')

   1           MAP_ADD                  1

  11           LOAD_CONST              18 ('J')
               LOAD_CONST              19 ('Heather ')

   1           MAP_ADD                  1

  12           LOAD_CONST              20 ('K')
               LOAD_CONST              21 ('Petunia ')

   1           MAP_ADD                  1

  13           LOAD_CONST              22 ('L')
               LOAD_CONST              23 ('Gladiolus ')

   1           MAP_ADD                  1

  14           LOAD_CONST              24 ('M')
               LOAD_CONST              25 ('Yarrow ')

   1           MAP_ADD                  1

  15           LOAD_CONST              26 ('N')
               LOAD_CONST              27 ('Wisteria ')

   1           MAP_ADD                  1

  16           LOAD_CONST              28 ('O')
               LOAD_CONST              29 ('Hibiscus ')

   1           MAP_ADD                  1

  17           LOAD_CONST              30 ('P')
               LOAD_CONST              31 ('Edelweiss ')

   1           MAP_ADD                  1

  18           LOAD_CONST              32 ('Q')
               LOAD_CONST              33 ('Iris ')

   1           MAP_ADD                  1
               BUILD_MAP                0

  19           LOAD_CONST              34 ('R')
               LOAD_CONST              35 ('Anemone ')

   1           MAP_ADD                  1

  20           LOAD_CONST              36 ('S')
               LOAD_CONST              37 ('Kalmia ')

   1           MAP_ADD                  1

  21           LOAD_CONST              38 ('T')
               LOAD_CONST              39 ('Zinnia ')

   1           MAP_ADD                  1

  22           LOAD_CONST              40 ('U')
               LOAD_CONST              41 ('Lotus ')

   1           MAP_ADD                  1

  23           LOAD_CONST              42 ('V')
               LOAD_CONST              43 ('Oleander ')

   1           MAP_ADD                  1

  24           LOAD_CONST              44 ('W')
               LOAD_CONST              45 ('Begonia ')

   1           MAP_ADD                  1

  25           LOAD_CONST              46 ('X')
               LOAD_CONST              47 ('Foxglove ')

   1           MAP_ADD                  1

  26           LOAD_CONST              48 ('Y')
               LOAD_CONST              49 ('Sunflower ')

   1           MAP_ADD                  1

  27           LOAD_CONST              50 ('Z')
               LOAD_CONST              51 ('Dahlia ')

   1           MAP_ADD                  1

  29           LOAD_CONST              52 ('a')
               LOAD_CONST              53 ('Jasmine ')

   1           MAP_ADD                  1

  30           LOAD_CONST              54 ('b')
               LOAD_CONST              55 ('Freesia ')

   1           MAP_ADD                  1

  31           LOAD_CONST              56 ('c')
               LOAD_CONST              57 ('Bluebell ')

   1           MAP_ADD                  1

  32           LOAD_CONST              58 ('d')
               LOAD_CONST              59 ('Aconite ')

   1           MAP_ADD                  1

  33           LOAD_CONST              60 ('e')
               LOAD_CONST              61 ('Orchid ')

   1           MAP_ADD                  1

  34           LOAD_CONST              62 ('f')
               LOAD_CONST              63 ('Azalea ')

   1           MAP_ADD                  1

  35           LOAD_CONST              64 ('g')
               LOAD_CONST              65 ('Carnation ')

   1           MAP_ADD                  1

  36           LOAD_CONST              66 ('h')
               LOAD_CONST              67 ('Ursinia ')

   1           MAP_ADD                  1
               DICT_UPDATE              1
               BUILD_MAP                0

  37           LOAD_CONST              68 ('i')
               LOAD_CONST              69 ('Gardenia ')

   1           MAP_ADD                  1

  38           LOAD_CONST              70 ('j')
               LOAD_CONST              71 ('Snowdrop ')

   1           MAP_ADD                  1

  39           LOAD_CONST              72 ('k')
               LOAD_CONST              73 ('Marigold ')

   1           MAP_ADD                  1

  40           LOAD_CONST              74 ('l')
               LOAD_CONST              75 ('Nerine ')

   1           MAP_ADD                  1

  41           LOAD_CONST              76 ('m')
               LOAD_CONST              77 ('Aster ')

   1           MAP_ADD                  1

  42           LOAD_CONST              78 ('n')
               LOAD_CONST              79 ('Xeranthemum ')

   1           MAP_ADD                  1

  43           LOAD_CONST              80 ('o')
               LOAD_CONST              81 ('Peony ')

   1           MAP_ADD                  1

  44           LOAD_CONST              82 ('p')
               LOAD_CONST              83 ('Daisy ')

   1           MAP_ADD                  1

  45           LOAD_CONST              84 ('q')
               LOAD_CONST              85 ('Buttercup ')

   1           MAP_ADD                  1

  46           LOAD_CONST              86 ('r')
               LOAD_CONST              87 ('Primula ')

   1           MAP_ADD                  1

  47           LOAD_CONST              88 ('s')
               LOAD_CONST              89 ('Crocus ')

   1           MAP_ADD                  1

  48           LOAD_CONST              90 ('t')
               LOAD_CONST              91 ('Verbena ')

   1           MAP_ADD                  1

  49           LOAD_CONST              92 ('u')
               LOAD_CONST              93 ('Snapdragon ')

   1           MAP_ADD                  1

  50           LOAD_CONST              94 ('v')
               LOAD_CONST              95 ('Cosmos ')

   1           MAP_ADD                  1

  51           LOAD_CONST              96 ('w')
               LOAD_CONST              97 ('Delphinium ')

   1           MAP_ADD                  1

  52           LOAD_CONST              98 ('x')
               LOAD_CONST              99 ('Fuchsia ')

   1           MAP_ADD                  1

  53           LOAD_CONST             100 ('y')
               LOAD_CONST             101 ('Primrose ')

   1           MAP_ADD                  1
               DICT_UPDATE              1
               BUILD_MAP                0

  54           LOAD_CONST             102 ('z')
               LOAD_CONST             103 ('Scabiosa ')

   1           MAP_ADD                  1

  56           LOAD_CONST             104 ('0')
               LOAD_CONST             105 ('Hydrangea ')

   1           MAP_ADD                  1

  57           LOAD_CONST             106 ('1')
               LOAD_CONST             107 ('Amaranth ')

   1           MAP_ADD                  1

  58           LOAD_CONST             108 ('2')
               LOAD_CONST             109 ('Clematis ')

   1           MAP_ADD                  1

  59           LOAD_CONST             110 ('3')
               LOAD_CONST             111 ('Pansy ')

   1           MAP_ADD                  1

  60           LOAD_CONST             112 ('4')
               LOAD_CONST             113 ('Daffodil ')

   1           MAP_ADD                  1

  61           LOAD_CONST             114 ('5')
               LOAD_CONST             115 ('Lilac ')

   1           MAP_ADD                  1

  62           LOAD_CONST             116 ('6')
               LOAD_CONST             117 ('Calla ')

   1           MAP_ADD                  1

  63           LOAD_CONST             118 ('7')
               LOAD_CONST             119 ('Phlox ')

   1           MAP_ADD                  1

  64           LOAD_CONST             120 ('8')
               LOAD_CONST             121 ('Geranium ')

   1           MAP_ADD                  1

  65           LOAD_CONST             122 ('9')
               LOAD_CONST             123 ('Amaryllis ')

   1           MAP_ADD                  1

  66           LOAD_CONST             124 ('{')
               LOAD_CONST             125 ('Canna ')

   1           MAP_ADD                  1

  67           LOAD_CONST             126 ('}')
               LOAD_CONST             127 ('Silene ')

   1           MAP_ADD                  1

  68           LOAD_CONST             128 ('_')
               LOAD_CONST             129 ('Thistle ')

   1           MAP_ADD                  1

  69           LOAD_CONST             130 ('+')
               LOAD_CONST             131 ('Lotuswort ')

   1           MAP_ADD                  1

  70           LOAD_CONST             132 ('\\')
               LOAD_CONST             133 ('Anthurium ')

   1           MAP_ADD                  1

  71           LOAD_CONST             134 ("'")
               LOAD_CONST             135 ('Viola ')

   1           MAP_ADD                  1
               DICT_UPDATE              1

  72           LOAD_CONST             136 ('Cyclamen ')

  73           LOAD_CONST             137 ('Ixora ')

   1           LOAD_CONST             138 ((' ', ':'))
               BUILD_CONST_KEY_MAP      2
               DICT_UPDATE              1
               STORE_NAME               0 (flower_bouquet)

  77           LOAD_NAME                0 (flower_bouquet)
               LOAD_ATTR                3 (items + NULL|self)
               CALL                     0
               GET_ITER
               LOAD_FAST_AND_CLEAR      0 (seed)
               LOAD_FAST_AND_CLEAR      1 (bouquet)
               SWAP                     3
       L1:     BUILD_MAP                0
               SWAP                     2
               GET_ITER
       L2:     FOR_ITER                 7 (to L3)
               UNPACK_SEQUENCE          2
               STORE_FAST_STORE_FAST    1 (seed, bouquet)
               LOAD_FAST_LOAD_FAST     16 (bouquet, seed)
               MAP_ADD                  2
               JUMP_BACKWARD            9 (to L2)
       L3:     END_FOR
               POP_TOP
       L4:     SWAP                     3
               STORE_FAST               1 (bouquet)
               STORE_FAST               0 (seed)
               STORE_NAME               2 (bouquet_flower)

  79           LOAD_CONST             139 (<code object build_bouquet at 0x7f1670ef4d30, file "chall.py", line 79>)
               MAKE_FUNCTION
               STORE_NAME               3 (build_bouquet)

  82           LOAD_CONST             140 (<code object disassemble_bouquet at 0x7f1670f2eaf0, file "chall.py", line 82>)
               MAKE_FUNCTION
               STORE_NAME               4 (disassemble_bouquet)

  86           LOAD_CONST             141 (<code object main at 0x7f1670d856f0, file "chall.py", line 86>)
               MAKE_FUNCTION
               STORE_NAME               5 (main)

  95           LOAD_NAME                6 (__name__)
               LOAD_CONST             142 ('__main__')
               COMPARE_OP              88 (bool(==))
               POP_JUMP_IF_FALSE        8 (to L5)

  96           LOAD_NAME                5 (main)
               PUSH_NULL
               CALL                     0
               POP_TOP
               RETURN_CONST           143 (None)

  95   L5:     RETURN_CONST           143 (None)

  --   L6:     SWAP                     2
               POP_TOP

  77           SWAP                     3
               STORE_FAST               1 (bouquet)
               STORE_FAST               0 (seed)
               RERAISE                  0
ExceptionTable:
  L1 to L4 -> L6 [3]

Disassembly of <code object build_bouquet at 0x7f1670ef4d30, file "chall.py", line 79>:
 79           RESUME                   0

 80           LOAD_CONST               1 ('')
              LOAD_ATTR                1 (join + NULL|self)
              LOAD_CONST               2 (<code object <genexpr> at 0x7f1670ef5630, file "chall.py", line 80>)
              MAKE_FUNCTION
              LOAD_FAST                0 (seed_line)
              GET_ITER
              CALL                     0
              CALL                     1
              RETURN_VALUE

Disassembly of <code object <genexpr> at 0x7f1670ef5630, file "chall.py", line 80>:
  80           RETURN_GENERATOR
               POP_TOP
       L1:     RESUME                   0
               LOAD_FAST                0 (.0)
               GET_ITER
       L2:     FOR_ITER                14 (to L3)
               STORE_FAST               1 (seed)
               LOAD_GLOBAL              0 (flower_bouquet)
               LOAD_FAST                1 (seed)
               BINARY_SUBSCR
               YIELD_VALUE              0
               RESUME                   5
               POP_TOP
               JUMP_BACKWARD           16 (to L2)
       L3:     END_FOR
               POP_TOP
               RETURN_CONST             0 (None)

  --   L4:     CALL_INTRINSIC_1         3 (INTRINSIC_STOPITERATION_ERROR)
               RERAISE                  1
ExceptionTable:
  L1 to L4 -> L4 [0] lasti

Disassembly of <code object disassemble_bouquet at 0x7f1670f2eaf0, file "chall.py", line 82>:
 82           RESUME                   0

 83           LOAD_FAST                0 (arrangement)
              LOAD_ATTR                1 (split + NULL|self)
              LOAD_CONST               1 (' ')
              CALL                     1
              STORE_FAST               1 (stems)

 84           LOAD_CONST               2 ('')
              LOAD_ATTR                3 (join + NULL|self)
              LOAD_CONST               3 (<code object <genexpr> at 0x7f1670f2ec10, file "chall.py", line 84>)
              MAKE_FUNCTION
              LOAD_FAST                1 (stems)
              GET_ITER
              CALL                     0
              CALL                     1
              RETURN_VALUE

Disassembly of <code object <genexpr> at 0x7f1670f2ec10, file "chall.py", line 84>:
  84           RETURN_GENERATOR
               POP_TOP
       L1:     RESUME                   0
               LOAD_FAST                0 (.0)
               GET_ITER
       L2:     FOR_ITER                25 (to L5)
               STORE_FAST_LOAD_FAST    17 (bouquet, bouquet)
               TO_BOOL
       L3:     POP_JUMP_IF_TRUE         2 (to L4)
               JUMP_BACKWARD           11 (to L2)
       L4:     LOAD_GLOBAL              0 (bouquet_flower)
               LOAD_FAST                1 (bouquet)
               LOAD_CONST               0 (' ')
               BINARY_OP                0 (+)
               BINARY_SUBSCR
               YIELD_VALUE              0
               RESUME                   5
               POP_TOP
               JUMP_BACKWARD           27 (to L2)
       L5:     END_FOR
               POP_TOP
               RETURN_CONST             1 (None)

  --   L6:     CALL_INTRINSIC_1         3 (INTRINSIC_STOPITERATION_ERROR)
               RERAISE                  1
ExceptionTable:
  L1 to L3 -> L6 [0] lasti
  L4 to L6 -> L6 [0] lasti

Disassembly of <code object main at 0x7f1670d856f0, file "chall.py", line 86>:
 86           RESUME                   0

 91           LOAD_CONST               1 ('Rose Cyclamen Crocus Daisy Orchid Bluebell Gardenia Jasmine Nerine Cyclamen Freesia Peony Snapdragon Buttercup Snapdragon Orchid Verbena Cyclamen Azalea Peony Primula Cyclamen Jasmine Cyclamen Crocus Daisy Orchid Bluebell Gardenia Jasmine Nerine Cyclamen Crocus Peony Aster Orchid Peony Xeranthemum Orchid Ixora Cyclamen Violet Magnolia Kalmia Canna Bluebell Viola Orchid Crocus Verbena Thistle Nerine Jasmine Thistle Cosmos Gardenia Orchid Thistle Orchid Xeranthemum Thistle Primula Peony Crocus Orchid Silene')
              STORE_FAST               0 (special_bouquet)
              RETURN_CONST             0 (None)
```

From the bytecodes, we can see that it's mapping values to flower names. And, based on the challenge description, we are supposed to arrange the flowers in a "bouquet" and translate it to the mapped character to get the flag.

I drafted the decoder with the help of Claude:
```
#!/usr/bin/env python3

# Create the flower mapping dictionary from the bytecode
flower_bouquet = {
    'A': 'Rose ', 'B': 'Camellia ', 'C': 'Magnolia ', 'D': 'Poppy ', 'E': 'Tulip ',
    'F': 'Chrysanthemum ', 'G': 'Hyacinth ', 'H': 'Violet ', 'I': 'Lavender ', 'J': 'Heather ',
    'K': 'Petunia ', 'L': 'Gladiolus ', 'M': 'Yarrow ', 'N': 'Wisteria ', 'O': 'Hibiscus ',
    'P': 'Edelweiss ', 'Q': 'Iris ', 'R': 'Anemone ', 'S': 'Kalmia ', 'T': 'Zinnia ',
    'U': 'Lotus ', 'V': 'Oleander ', 'W': 'Begonia ', 'X': 'Foxglove ', 'Y': 'Sunflower ',
    'Z': 'Dahlia ', 'a': 'Jasmine ', 'b': 'Freesia ', 'c': 'Bluebell ', 'd': 'Aconite ',
    'e': 'Orchid ', 'f': 'Azalea ', 'g': 'Carnation ', 'h': 'Ursinia ', 'i': 'Gardenia ',
    'j': 'Snowdrop ', 'k': 'Marigold ', 'l': 'Nerine ', 'm': 'Aster ', 'n': 'Xeranthemum ',
    'o': 'Peony ', 'p': 'Daisy ', 'q': 'Buttercup ', 'r': 'Primula ', 's': 'Crocus ',
    't': 'Verbena ', 'u': 'Snapdragon ', 'v': 'Cosmos ', 'w': 'Delphinium ', 'x': 'Fuchsia ',
    'y': 'Primrose ', 'z': 'Scabiosa ', '0': 'Hydrangea ', '1': 'Amaranth ', '2': 'Clematis ',
    '3': 'Pansy ', '4': 'Daffodil ', '5': 'Lilac ', '6': 'Calla ', '7': 'Phlox ',
    '8': 'Geranium ', '9': 'Amaryllis ', '{': 'Canna ', '}': 'Silene ', '_': 'Thistle ',
    '+': 'Lotuswort ', '\\': 'Anthurium ', "'": 'Viola ', ' ': 'Cyclamen ', ':': 'Ixora '
}

# Create reverse mapping (flower to character)
bouquet_flower = {v: k for k, v in flower_bouquet.items()}

# The encoded message from the bytecode
special_bouquet = 'Rose Cyclamen Crocus Daisy Orchid Bluebell Gardenia Jasmine Nerine Cyclamen Freesia Peony Snapdragon Buttercup Snapdragon Orchid Verbena Cyclamen Azalea Peony Primula Cyclamen Jasmine Cyclamen Crocus Daisy Orchid Bluebell Gardenia Jasmine Nerine Cyclamen Crocus Peony Aster Orchid Peony Xeranthemum Orchid Ixora Cyclamen Violet Magnolia Kalmia Canna Bluebell Viola Orchid Crocus Verbena Thistle Nerine Jasmine Thistle Cosmos Gardenia Orchid Thistle Orchid Xeranthemum Thistle Primula Peony Crocus Orchid Silene'

def disassemble_bouquet(arrangement):
    """Convert flower names back to characters"""
    stems = arrangement.split(' ')
    result = ''
    for bouquet in stems:
        if bouquet:  # Skip empty strings
            flower_key = bouquet + ' '  # Add space back since flowers have trailing space
            if flower_key in bouquet_flower:
                result += bouquet_flower[flower_key]
    return result

# Decode the flag
decoded_flag = disassemble_bouquet(special_bouquet)
print(f"Decoded flag: {decoded_flag}")

# Show the decoding process
print("\nDecoding process:")
flowers = special_bouquet.split(' ')
for i, flower in enumerate(flowers):
    if flower:  # Skip empty strings
        flower_key = flower + ' '
        char = bouquet_flower.get(flower_key, '?')
        print(f"{flower} -> {char}")
```

Running it gives us the flag:

![alt text](image-1.png)

Flag: ```HCS{c'est_la_vie_en_rose}```
