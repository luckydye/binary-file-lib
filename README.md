# A Library to read binary files in JS

## Example

```
import { BinaryFile } from 'binary-file-lib';

const FileHeader = {
    magic: 'char[4]'
}

class SomeBinaryFile extends BinaryFile {

    static parseFile(file) {
        // read file header
        file.header = this.unserialize(file, 0, FileHeader);
    }

    toString() {
        // get value from file header
        return BinaryFile.getValue(file.header, 'magic');
    }

}

function main(filename) {
    const fileBuffer = fs.readFileSync(path.resolve(filename));

    // create instance of file
    const file = new SomeBinaryFile(fileBuffer.buffer);

    console.log(file.toString());
}

```
