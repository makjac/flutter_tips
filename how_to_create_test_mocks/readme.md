1. First install required packages:
```console
flutter pub add http dev:mockito dev:build_runner
```
2. Add @GenerateMocks
```code
import 'package:http/http.dart' as http;
import 'package:mocking/main.dart';
import 'package:mockito/annotations.dart';

// Generate a MockClient using the Mockito package.
// Create new instances of this class in each test.
@GenerateMocks([http.Client])
void main() {
}
```

3. run build generator
```console
flutter pub run build_runner build --delete-conflicting-outputs
```

4. Import mockFile into your test file:
```Code
import 'package:http/http.dart' as http;
import 'package:mocking/main.dart';
import 'package:mockito/annotations.dart';
import 'remote_auth_datasource_test.mocks.dart';

@GenerateMocks([http.Client])
void main() {
  late MockClient mockClient;
  late RemoteAuthSource datasource;

  setUp(() {
    mockClient = MockClient();
    datasource = RemoteAuthSourceImpl(client: mockClient);
  });
```

