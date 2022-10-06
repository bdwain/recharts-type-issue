# RECHARTS TYPE ISSUE

run `npm test` to see the type error in the library's d.ts files

```
node_modules/recharts/types/component/LabelList.d.ts:21:70 - error TS2344: Type 'T' does not satisfy the constraint 'Data'.

21 export declare type Props<T> = SVGProps<SVGElement> & LabelListProps<T>;
                                                                        ~

  node_modules/recharts/types/component/LabelList.d.ts:21:27
    21 export declare type Props<T> = SVGProps<SVGElement> & LabelListProps<T>;
                                 ~
    This type parameter might need an `extends Data` constraint.

Found 1 error in node_modules/recharts/types/component/LabelList.d.ts:21
```

it occurs when strict (in tsconfig) is true and using a newer version of typescript

it is not causing issues when building recharts itself because its own tsconfig does not set strict to true, but a strict project should be able to use recharts without setting skipLibCheck to true, which skips checks for ALL libraries