# FieldTransform

Describes the difference between two Streams.


## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `AddField`                                                                        | [*FieldAdd](../../models/shared/fieldadd.md)                                      | :heavy_minus_sign:                                                                | N/A                                                                               |
| `Breaking`                                                                        | *bool*                                                                            | :heavy_check_mark:                                                                | N/A                                                                               |
| `FieldName`                                                                       | []*string*                                                                        | :heavy_check_mark:                                                                | A field name is a list of strings that form the path to the field.                |
| `RemoveField`                                                                     | [*FieldRemove](../../models/shared/fieldremove.md)                                | :heavy_minus_sign:                                                                | N/A                                                                               |
| `TransformType`                                                                   | [FieldTransformTransformType](../../models/shared/fieldtransformtransformtype.md) | :heavy_check_mark:                                                                | N/A                                                                               |
| `UpdateFieldSchema`                                                               | [*FieldSchemaUpdate](../../models/shared/fieldschemaupdate.md)                    | :heavy_minus_sign:                                                                | N/A                                                                               |