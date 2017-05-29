# vandy-add-2-ImageDownloader

# Overview 

1. The original resource is from gitlab.com/vandy-aad-2/ImageDownloader
2. At the point of investigating the source file mentioned above, there were few missing implementations and relevent comments
3. The source files in this repository has been updated with the missing implementations and relevant comments
4. However it is not the latest source code as per the original source
5. Pull the source code into an Android Studio environment and launch it Andriod Emulator

# Workflow / Explanations

1. This is an Image Downloader App that uses the `android.os.AsyncTask` Framework to perform the downloading task that usually a long duration process.
2. The `AsyncTask` Framework requires 2 method implementations, namely `doInBackground` and `onPostExecute`.
3. The `doInBackground` usually does the heavy lifting work then the result will returned and in turns passed into `onPostExecute`
4. It is also important for the `onPostExecute` to call the `finish()` method that usually comes as a superclass method
5. During the processing in `onPostExecute`, developers are responsible for *setting the Results* which indicates the upstream activity status and the downstream `Intent` object
6. Assuming that developer uses the `startActivityForResult` method, then the Caller Activity is expected to have the `onActivityResult` method being called
