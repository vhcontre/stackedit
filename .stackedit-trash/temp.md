**Refactorización de pruebas y código de repositorio para pedidos de inventario**

1. **Pruebas:**
   - Actualizadas las pruebas en `InventoryOrdersRepositoryGetTest+GroupedByFilter.cs`:
     * Reemplazado `RandomHelper` por `Random` nativo
     * Cambiado `FluentAssertions` por `Assert` estándar
     * Eliminadas dependencias a `FluentAssertions` y `Microsoft.Data.Sqlite`
     * Eliminados comentarios XML redundantes

2. **Refactorizaciones de código:**
   - `DeliveryNoteDetailViewModelMappingService.cs`:
     * Código reorganizado para mayor claridad
     * Eliminados comentarios XML redundantes

   - `InventoryOrdersRepository.cs`:
     * Eliminados los comentarios sobre métodos obsoletos
     * Eliminados comentarios XML redundantes

3. **Eliminaciones:**
   - `RandomHelper.cs` 
   - `RefactorAttribute.cs` 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NTE5MDAzODFdfQ==
-->