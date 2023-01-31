This project is for learning (Studio)[https://github.com/foxglove/studio], it inrroduces the related concept in the Studio

# Web

- `LocalstorageAppConfiguration` in Index
- `LDblayourstorage` in Root --> IdbLayoutStorage (class)： 创建 layourid，存储 layout--> ILayoutStorage (Interface)
- Layout:
- `App` in Root, Suppress context menu for the entire app except on inputs & textareas.
- `provider`: Providers pass data to a subtree.
- `IDataSourceFactory`: 是其他所有Ros类型的父类factory，有id


# Provider

- `PanelCatalogProvider`: get registed panel info from **@foxglove/studio-base/components/Panel/index** and ExtensionPanels

# Component
- `PlayerManager`：管理数据，判断数据类型，loading data, return <PlayerSelectionContext.Provider> and <MessagePipelineProvider>
- `GlobalCss`: 全局渲染

# Servce
- `IdbExtensionLoader`: Will help to find the Customer Extension

# Players
   ```Chain of references
   LocalDataSourceFactory[DataSources]--> IterablePlayer
                                          ├──> IterableSource
                                          ├──> IteratorResult
                                          └──> BufferedIterableSource(IIterableSource)-->CachingIterableSource
                                           
   ```SocketDataSourceFactory[DataSources]--> Player
# React
- `StrictMode`: It activates additional checks and warnings for its descendants.
- `Promise`: A Promise is a proxy for a value not necessarily known when the promise is created. It allows you to associate handlers with an asynchronous action's eventual success value or failure reason.
- useMemo: Think of memoization as caching a value so that it does not need to be recalculated. This can improve performance.可以通过向其传递一些参数来影响某些函数的执行, React 检查这些参数是否已更改，并且只有在存在差异的情况下才会执行此。传入 - useMemo 的函数会在**渲染期间**执行. useMemo(function，监听参数)
- useState: 让函数式组件拥有状态管理特性, const [count, setCount] = useState<number>(initial)
- useEffect: By using this Hook, you tell React that your component needs to do something **after render**. By default, it runs both after the first render and after every update.
- useCallback: useCallback is a React Hook that lets you cache a function definition between re-renders.


  ```
  useEffect(() => {
  document.title = `You clicked ${count} times`;
  }, [count]); // Only re-run the effect if count changes
  ```

- useRef: 它不仅仅是用来管理 DOM ref 的，它还相当于 this , 可以存放任何变量，很好的解决闭包带来的不方便性。 因为变更 .current 属性不会引发组件重新渲染

  ```
  countRef = useRef<number>(count)
  useEffect(() => {
  countRef.current = count
  })
  ```
