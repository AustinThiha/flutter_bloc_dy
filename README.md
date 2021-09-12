# flutter_bloc_dy


## BLOC

```
class CustomBloc<T> extends Bloc<CustomEvent, CustomState<T>> {

  CustomBloc() : super(CustomInitial<T>());

  @override
  Stream<CustomState<T>> mapEventToState(
    CustomEvent event,
  ) async* {
    if (event is LoginEvent) {
        //login process
    }
  }
}
```

## Event

```
@immutable
abstract class CustomEvent {}

class LoginEvent extends CustomEvent {
  final String name;
  final String password;

  LoginEvent(this.name, this.password);
}
```

## State

```
@immutable
abstract class CustomState<ReturnModel> {}

class CustomInitial<ReturnModel> extends CustomState<ReturnModel> {}

class CustomLoadingState<ReturnModel> extends CustomState<ReturnModel> {}

class CustomSuccessState<ReturnModel> extends CustomState<ReturnModel> {
  final List<ReturnModel> list;

  CustomSuccessState(this.list);
}

class CustomFailState<ReturnModel> extends CustomState<ReturnModel> {
  final ApiError apiError;

  CustomFailState(this.apiError);
}
```
