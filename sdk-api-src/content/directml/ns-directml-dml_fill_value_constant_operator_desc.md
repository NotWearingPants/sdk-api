---
UID: NS:directml.DML_FILL_VALUE_CONSTANT_OPERATOR_DESC
title: DML_FILL_VALUE_CONSTANT_OPERATOR_DESC
description: Fills a tensor with the given constant *Value*.
helpviewer_keywords: ["DML_FILL_VALUE_CONSTANT_OPERATOR_DESC","DML_FILL_VALUE_CONSTANT_OPERATOR_DESC structure","direct3d12.dml_fill_value_constant_operator_desc","directml/DML_FILL_VALUE_CONSTANT_OPERATOR_DESC"]
tech.root: directml
ms.date: 10/30/2020
req.header: directml.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
f1_keywords:
 - DML_FILL_VALUE_CONSTANT_OPERATOR_DESC
 - directml/DML_FILL_VALUE_CONSTANT_OPERATOR_DESC
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DirectML.h
api_name:
 - DML_FILL_VALUE_CONSTANT_OPERATOR_DESC
---

## -description

Fills a tensor with the given constant *Value*. This operator performs the following pseudocode.

```
for each coordinate in OutputTensor
    OutputTensor[coordinate] = Value
endfor
```

## -struct-fields

### -field OutputTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

The tensor to write the results to. This tensor may have any size.

### -field ValueDataType

Type: **[DML_TENSOR_DATA_TYPE](/windows/win32/api/directml/ne-directml-dml_tensor_data_type)**

The data type of the *Value* field, which must match *OutputTensor.DataType*.

### -field Value

Type: **[DML_SCALAR_UNION](/windows/win32/api/directml/ns-directml-dml_scalar_union)**

A constant value to fill the output, with *ValueDataType* determining how to interpret the field.

## Examples

```
Value = 13.0

OutputTensor: (Sizes:{1,1,2,4}, DataType:FLOAT32)
    [[[[13.0f, 13.0f, 13.0f, 13.0f],
       [13.0f, 13.0f, 13.0f, 13.0f]]]]
```

## Availability
This operator was introduced in `DML_FEATURE_LEVEL_2_1`.

## Tensor support

### DML_FEATURE_LEVEL_4_1 and above
| Tensor | Kind | Supported dimension counts | Supported data types |
| ------ | ---- | -------------------------- | -------------------- |
| OutputTensor | Output | 1 to 8 | FLOAT64, FLOAT32, FLOAT16, INT64, INT32, INT16, INT8, UINT64, UINT32, UINT16, UINT8 |

### DML_FEATURE_LEVEL_4_0 and above
| Tensor | Kind | Supported dimension counts | Supported data types |
| ------ | ---- | -------------------------- | -------------------- |
| OutputTensor | Output | 1 to 8 | FLOAT32, FLOAT16, INT32, INT16, INT8, UINT32, UINT16, UINT8 |

### DML_FEATURE_LEVEL_2_1 and above
| Tensor | Kind | Supported dimension counts | Supported data types |
| ------ | ---- | -------------------------- | -------------------- |
| OutputTensor | Output | 4 | FLOAT32, FLOAT16, INT32, INT16, INT8, UINT32, UINT16, UINT8 |
